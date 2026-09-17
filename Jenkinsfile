pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Vallabh04022006/assessment-7.3.git'
            }
        }

        stage('Parallel Checks') {
            parallel {
                stage('Frontend Check') {
                    steps {
                        bat 'C:\\Users\\Vallabh\\AppData\\Local\\Python\\bin\\python.exe frontend_check.py'
                    }
                }

                stage('Backend Check') {
                    steps {
                        bat 'C:\\Users\\Vallabh\\AppData\\Local\\Python\\bin\\python.exe backend_check.py'
                    }
                }
            }
        }

        stage('Summary') {
            steps {
                echo 'Both frontend and backend checks are complete.'
            }
        }
    }
}
