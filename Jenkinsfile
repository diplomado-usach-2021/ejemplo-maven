pipeline {
    agent any
    stages {
        stage('Compile') {
            steps {
                echo 'Compile Code'
                sh './mvnw clean compile -e'
            }
        }
        stage('Test') {
            steps {
                echo 'Test Code'
                sh './mvnw.cmd clean test -e'
            }
        }
        stage('Jar') {
            steps {
                echo 'Jar Code'
                sh './mvnw.cmd clean package -e'
            }
        }
    }
}
