pipeline {
  agent any
  stages {
    stage('Static Analysis') {
      post {
        always {
          archiveArtifacts 'campr-injection-workshop/build/reports/spotbugs/main.html'

        }

      }
      steps {
        sh '''cd campr-injection-workshop/
./gradlew check'''
      }
    }
  }
}