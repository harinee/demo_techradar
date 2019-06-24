pipeline {
  agent any
  stages {
    stage('Static Analysis') {
      steps {
        sh '''cd campr-injection-workshop/
./gradlew check'''
        archiveArtifacts 'build/reports/spotbugs/main.html'
      }
    }
  }
}