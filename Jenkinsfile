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
                sh './mvnw clean test -e'
            }
        }
        stage('Jar') {
            steps {
                echo 'Jar Code'
                sh './mvnw clean package -e'
            }
        }
        //stage('Run') {
        //    steps {
        //        echo 'Running'
        //        sh './mvnw spring-boot:run'
        //    }
        //}
        stage('SonarQube analysis') {
            steps {
                script{
                    def scannerHome = tool 'sq-local';
                    withSonarQubeEnv('sq') {
                        sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=SonarQube-S7M3"
                    }
                }
            }
        }        
    }
}
