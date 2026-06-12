pipeline {
    agent any

    tools {
        maven 'Maven'
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
        stage('Run Selenium') {
            steps {
                sh '''
                export DISPLAY=:0
                mvn exec:java -Dexec.mainClass="com.example.App"
                '''
            }
        }
    }

    post {
        success {
            echo "Selenium execution successful!"
        }
        failure {
            echo 'Build failed!'
        }
    }
}




