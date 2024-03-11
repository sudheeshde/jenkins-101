pipeline {
    agent { 
        node {
            label 'docker-agent-python'
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
    when {
        changeset 'master'
    }
}