pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh """
        python3 -m venv venv
        . venv/bin/activate
        pip install -r requirements.txt
        """
      }
    }
    stage('test') {
      steps {
        sh """
        . venv/bin/activate
        python -m unittest test.py
        """
      }
      post {
        always {
          sh 'rm -rf *'
        }
      }    
    }
  }
}
