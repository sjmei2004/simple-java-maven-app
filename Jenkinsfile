pipeline {
    agent  {
       label 'windows'
    }
    tools{
       maven 'mvn-3.8.8'
    }
    stages {
        stage('Build') {
            steps {
                bat 'mvn  clean package'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') {
            steps {
                bat './jenkins/scripts/deliver.sh'
            }
        }
    }
}
