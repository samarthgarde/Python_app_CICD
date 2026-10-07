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

        stage('Build') {
            steps {
                bat '"C:\\Users\\JCT\\AppData\\Local\\Programs\\Python\\Python312\\python.exe" -m compileall .'
            }
        }
    }
}
