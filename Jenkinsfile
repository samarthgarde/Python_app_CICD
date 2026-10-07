pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/samarthgarde/Python_app_CICD.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat '"C:\\Users\\JCT\\AppData\\Local\\Programs\\Python\\Python312\\python.exe" -m pip install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                bat '"C:\\Users\\JCT\\AppData\\Local\\Programs\\Python\\Python312\\python.exe" -m pytest'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    withCredentials([string(credentialsId: 'sonar-token', variable: 'SONAR_TOKEN')]) {
                        bat '"C:\\Users\\JCT\\Downloads\\sonar-scanner-cli-8.1.0.6389-windows-x64\\sonar-scanner-8.1.0.6389-windows-x64\\bin\\sonar-scanner.bat" -Dsonar.token=%SONAR_TOKEN%'
                    }
                }
            }
        }

        stage('Build') {
            steps {
                bat '"C:\\Users\\JCT\\AppData\\Local\\Programs\\Python\\Python312\\python.exe" -m compileall .'
            }
        }
    }
}