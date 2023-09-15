pipeline {
    agent  any
    tools{
       maven 'mvn-3.5.6'
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn  clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
            }
        }
    }
}
