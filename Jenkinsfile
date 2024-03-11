pipeline {
    agent { 
        node {
            label 'docker-agent-python'
            }
      }
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building - master"
                sh '''
                cd myapp
                pip install -r requirements.txt
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing - master"
                sh '''
                cd myapp
                python3 hello.py
                python3 hello.py --name=SudheeshR_main
                '''
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying - master'
                sh '''
                echo "deploying stuff.."
                '''
            }
        }
    }
}