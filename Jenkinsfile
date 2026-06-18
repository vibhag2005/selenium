pipeline {
    agent any  // Use any available agent

    tools {
        maven 'maventest'  // Ensure this matches the name configured in Jenkins
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/vibhag2005/selenium.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'  
        }
}
        stage('Test') {
            steps {
                sh 'mvn test'  
            }
        }
        
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
