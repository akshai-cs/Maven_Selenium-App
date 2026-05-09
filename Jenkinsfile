pipeline {
    agent any

    tools {
        maven 'maven'
    }

    stages {
    	stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/akshai-cs/Maven_Selenium-App.git'
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
        stage('Run Application') {
            steps {
                // Start the JAR application
                sh 'java -jar target/2023MavenSeleniumApp-1.0-SNAPSHOT.jar'
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




