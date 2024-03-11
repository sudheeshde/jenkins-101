pipeline {
    agent { 
        node {
            label 'docker-agent-python'
            }
      }
    triggers {
        scm('**')
        branches('master')
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                cd myapp
                pip install -r requirements.txt
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                cd myapp
                python3 hello.py
                python3 hello.py --name=Sudheesh_R
                '''
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh '''
                echo "deploying stuff.."
                '''
            }
        }
    }
}