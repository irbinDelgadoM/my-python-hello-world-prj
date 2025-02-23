pipeline {
    agent { 
        node {
            label 'jenkins-worker-1'
            }
      }
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                cd myapp
                python3 -m venv venv
                bash -c "source venv/bin/activate && echo 'Virtual environment activated!'"
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
                python3 hello.py --name=Irbin
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo "Deliver.."
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
}
