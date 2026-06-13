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
		sh 'java -jar target/2023MavenSeleniumApp-1.0-SNAPSHOT.jar'
            }
        }
    }

    post {
        success {
            echo "Selenium execution successful!"
	    echo "Open SauceDemo: https://www.saucedemo.com"
        }
        failure {
            echo 'Build failed!'
        }
    }
}




