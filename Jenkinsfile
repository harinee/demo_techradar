pipeline {
  agent any
  stages {
    stage('Static Analysis') {
      steps {
        sh '''cd campr-injection-workshop/
./gradlew check'''
      }
      post {
        always {
             archiveArtifacts(artifacts: 'build/reports/spotbugs/main.html')
        }
      }  
      }
    }
  }
}
