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
        stage('Build - master') {
            steps {
                echo "Building.."
                sh '''
                cd myapp
                pip install -r requirements.txt
                '''
            }
        }
        stage('Test - master') {
            steps {
                echo "Testing.."
                sh '''
                cd myapp
                python3 hello.py
                python3 hello.py --name=Sudheesh_R
                '''
            }
        }
        stage('Deploy - master') {
            steps {
                echo 'Deploying....'
                sh '''
                echo "deploying stuff.."
                '''
            }
        }
    }
}