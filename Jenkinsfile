pipeline {
  agent { label 'windows' } // Changed from 'linux' to 'windows'
  options {
    skipDefaultCheckout(true)
  }
  stages {
    stage('clean workspace') {
      steps {
        cleanWs()
      }
    }
    stage('checkout') {
      steps {
        checkout scm
      }
    }
    stage('terraform') {
      steps {
        bat 'terraform apply -auto-approve -no-color' // Changed from 'sh' to 'bat' and removed './terraformw'
      }
    }
  }
  post {
    always {
      cleanWs()
    }
  }
}