pipeline {
    agent  any
    tools{
       maven 'mvn-3.6.2'
    }
    stages {
        stage('Build') {
            steps {
                cmd 'mvn  clean package'
            }
        }
        stage('Test') {
            steps {
                cmd 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') {
            steps {
                cmd './jenkins/scripts/deliver.sh'
            }
        }
    }
}
