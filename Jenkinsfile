pipeline {
  agent any
  stages {
    stage('Static Analysis') {
      steps {
        sh '''cd campr-injection-workshop/
./gradlew check'''
        archiveArtifacts 'demo_techradar_jenkins/campr-injection-workshop/build/reports/spotbugs/main.html'
      }
    }
  }
}