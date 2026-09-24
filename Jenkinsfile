pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/msshabreena-coder/Jenkins-Q7.git'
            }
        }

        stage('Build') {
            steps {
                bat 'python -m py_compile app.py'
                bat 'timeout /t 15 /nobreak'
                milestone(1)
            }
        }

        stage('Send Notification') {
            steps {
                echo "To: msshabreena@gmail.com"
                echo "Subject: ${JOB_NAME} - Build #${BUILD_NUMBER}"
                echo "Build URL: ${BUILD_URL}"
            }
        }
    }
}
