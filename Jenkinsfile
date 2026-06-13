pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git branch: 'main',
                url: 'https://github.com/Sahilhub22/Hospital-Management-System.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                pkill -f run.py || true
                nohup python3 run.py > app.log 2>&1 &
                '''
            }
        }
    }
}
