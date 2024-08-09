pipeline {
    agent any

    tools {
        maven 'Maven'  // Name of the Maven installation configured in Jenkins
        jdk 'JDK 21.0'      // Name of the JDK installation configured in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                // Clone the repository
                git branch: 'main', url: 'https://github.com/mgidw/pip1.git'
            }
        }

        stage('Build') {
            steps {
                // Run Maven build
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                // Run tests
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                // Package the application
                sh 'mvn package'
            }
        }

        stage('Deploy') {
            steps {
                // Deploy the application (adjust according to your deployment strategy)
                sh 'echo "Deploying application..."'
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
