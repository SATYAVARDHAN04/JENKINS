pipeline {
    agent {
        label 'AGENT1'
    }

    environment {
        COURSE='Devops'
    }

    options {
        disableConcurrentBuilds()
        timeout(time:30, unit:'MINUTES')
    }

    parameters {
        string(name: 'BRANCH', defaultValue: 'CSE', description: 'BRANCH name')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                echo "${COURSE} is very good"
                echo "${params.BRANCH} is bad"
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }

    post {
        always {
            echo 'This will always run'
            //deleteDir()
        }
        success {
            echo 'This will run only if the build succeeds'
        }
        failure {
            echo 'This will run only if the build fails'
        }
    }
}