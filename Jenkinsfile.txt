pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Build Successful'
            }
        }

        stage('Deploy') {
            steps {
                sh 'kubectl apply -f deployment.yaml'
                sh 'kubectl apply -f service.yaml'
            }
        }
    }
}
