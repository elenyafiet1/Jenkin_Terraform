pipeline {
    agent any

    tools {
        git 'Git' // Ensure this matches the Git configuration in Jenkins
    }

    stages {
        stage('Checkout SCM') {
            steps {
                checkout scm
            }
        }
    }
}
