pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'sh \'mvn -B -DskipTests clean package\''
      }
    }

  }
}