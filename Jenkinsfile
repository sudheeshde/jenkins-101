pipeline {
    agent { 
        node {
            label 'docker-agent-python'
            }
    }
    stages {
        stage('Build') {
            when {
                changeset 'master'
            }
            steps {
                echo "Building.."
                sh '''
                cd myapp
                pip install -r requirements.txt
                '''
            }
        }
        stage('Test') {
            when {
                changeset 'master'
            }
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
            when {
                changeset 'master'
            }
            steps {
                echo 'Deploying....'
                sh '''
                echo "deploying stuff.."
                '''
            }
        }
    }
}