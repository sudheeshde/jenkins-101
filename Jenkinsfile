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
        stage('Build - dev') {
            steps {
                echo "Building - dev"
                sh '''
                cd myapp
                pip install -r requirements.txt
                '''
            }
        }
        stage('Test - dev') {
            steps {
                echo "Testing - dev"
                sh '''
                cd myapp
                python3 hello.py
                python3 hello.py --name=Sudheesh_R
                '''
            }
        }
        stage('Deploy - dev') {
            steps {
                echo 'Deploying - dev'
                sh '''
                echo "deploying stuff.."
                '''
            }
        }
    }
}