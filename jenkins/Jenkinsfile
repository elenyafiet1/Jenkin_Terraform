pipeline {
    agent any
    
    environment {
        TF_VAR_AWS_ACCESS_KEY = credentials('AKIAXKUH3BR5UBMBUDMV')  // Access the AWS Access Key ID
        TF_VAR_AWS_SECRET_KEY = credentials('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')   // Access the AWS Secret Access Key
    }

    stages {
        stage('Initialize Terraform') {
            steps {
                sh 'terraform init'
            }
        }
        stage('Plan Terraform') {
            steps {
                sh 'terraform plan'
            }
        }
        stage('Apply Terraform') {
            steps {
                input message: 'Proceed with Terraform apply?', ok: 'Yes'
                sh 'terraform apply -auto-approve'
            }
        }
    }
}
