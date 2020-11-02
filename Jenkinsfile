pipeline {
  agent {
    docker {
      image 'python:3.7.2'
    }

  }
  stages {
    stage('build') {
      steps {
        sh 'pip install -r requirements.txt --user'
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