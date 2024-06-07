pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    sh 'python -m venv venv'
                    sh 'source venv/bin/activate'
                    sh 'pip install -r requirements.txt'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    sh 'source venv/bin/activate'
                    sh 'pytest'
                }
            }
        }
    }

    post {
        always {
            junit 'test-results.xml'
        }
    }
}
