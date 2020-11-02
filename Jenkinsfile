pipeline {
  agent {
    docker {
      image 'python:3.7.2'
    }

  }
  stages {
    stage('build') {
      steps {
        sh 'sudo pip install -r requirements.txt'
      }
    }

    stage('test') {
      post {
        always {
          junit 'test-reports/*.xml'
        }

      }
      steps {
        sh 'python test_app.py'
      }
    }

  }
  environment {
    CI = 'true'
  }
}