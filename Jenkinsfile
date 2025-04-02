pipeline {
    agent any
    
    environment {
        AWS_ACCESS_KEY_ID = credentials('AKIAXKUH3BR5ZAS3J547')
        AWS_SECRET_ACCESS_KEY = credentials('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')
    }

    stages {
        stage('Verify AWS Credentials') {
            steps {
                sh 'aws sts get-caller-identity'
            }
        }
    }
}
