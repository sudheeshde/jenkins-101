pipeline {
    agent { 
        node {
            label 'docker-agent-python'
            }
      }
    triggers {
        scm('**') {  // Monitor all branches for changes
            branches('master')  // Only trigger for commits to the 'dev' branch
        }
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
                python3 hello.py --name=SudheeshR
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