pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh """
        python3 -m venv venv
        source venv/bin/activate
        pip install -r requirements.txt
        """
      }
    }
    stage('test') {
      steps {
        sh 'python test.py'
      }
      post {
        always {
          junit 'test-reports/*.xml'
        }
      }    
    }
  }
}
