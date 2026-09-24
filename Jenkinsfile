pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/msshabreena-coder/Jenkins-Q7.git'
            }
        }

        stage('Build') {
            steps {
                bat 'python -m py_compile app.py'
                bat 'ping 127.0.0.1 -n 16 > nul'
                milestone(1)
            }
        }

        stage('Send Notification') {
            steps {
                mail(
                    to: 'msshabreena@gmail.com',
                    subject: "${JOB_NAME} - Build #${BUILD_NUMBER}",
                    body: "Build URL: ${BUILD_URL}"
                )
            }
        }
    }
}
