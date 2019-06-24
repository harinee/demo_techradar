pipeline {
  agent any
  stages {
    stage('Static Analysis') {
      steps {
        sh './gradlew check'
      }
    }
  }
}