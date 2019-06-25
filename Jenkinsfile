pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          post {
            always {
              archiveArtifacts 'campr-injection-workshop/build/reports/spotbugs/main.html'

            }

          }
          steps {
            echo 'Building'
          }
        }
        stage('SAST') {
          steps {
            sh '''cd campr-injection-workshop/
./gradlew check'''
          }
        }
        stage('Dependency check') {
          steps {
            sh '''cd campr-injection-workshop
./gradlew dependencyCheckAnalyze'''
          }
        }
        stage('Secret scan') {
          steps {
            sh 'echo "Secret scan"'
          }
        }
      }
    }
    stage('Unit tests') {
      steps {
        echo 'Unit testing'
      }
    }
    stage('Deploy test env') {
      steps {
        echo 'Test env ready'
      }
    }
    stage('Functional tests') {
      parallel {
        stage('Functional tests') {
          steps {
            echo 'Functional tests'
          }
        }
        stage('DAST') {
          steps {
            echo 'ZAPing'
          }
        }
      }
    }
    stage('Deploy staging') {
      steps {
        echo 'Staging ready'
      }
    }
  }
}