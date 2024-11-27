pipeline {
    agent any // Use any available agent
    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the repository
                git branch: 'main', url: 'https://github.com/kanishk-paradiso/pipeline1_jenkins.git'
            }
        }
        stage('Build') {
            steps {
                // Run a build tool like Maven or npm
                sh 'mvn clean install' // Change this as per your project
            }
        }
        stage('Test') {
            steps {
                // Run tests
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                // Run deployment script
                sh './deploy.sh'
            }
        }
    }
    post {
        always {
            // Cleanup or notifications
            echo 'Pipeline completed!'
        }
        failure {
            // Notify on failure
            echo 'Pipeline failed!'
        }
    }
}
