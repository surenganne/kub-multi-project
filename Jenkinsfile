pipeline {
    agent master

    stages {
        stage('Build sa-frontend') {
            steps {
                sh 'cd ${WORKSPACE}/sa-frontend && npm install && npm run build'
            }
        }
        stage('Build sa-webapp') {
            steps {
                sh 'cd ${WORKSPACE}/sa-webapp && mvn install'
            }
        }
        stage('Build Docker sa-frontend') {
            steps {
                sh 'cd ${WORKSPACE}/sa-frontend && docker build -t sa-frontend .'
            }
        }
        stage('Build Docker sa-webapp') {
            steps {
                sh 'cd ${WORKSPACE}/sa-webapp && docker build -t sa-webapp .'
            }
        }
    }
}


