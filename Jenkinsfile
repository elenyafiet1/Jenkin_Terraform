pipeline {
    agent any

    environment {
        TF_VAR_AWS_ACCESS_KEY = credentials('AKIAXKUH3BR5ZAS3J547')
        TF_VAR_AWS_SECRET_KEY = credentials('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')
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/elenyafiet1/Jenkin_Terraform.git'
            }
        }
        
        stage('Initialize Terraform') {
            steps {
                sh 'terraform init'
            }
        }
        
        stage('Plan Terraform') {
            steps {
                sh 'terraform plan -out=tfplan'
            }
        }
        
        stage('Apply Terraform') {
            steps {
                input message: 'Proceed with Terraform apply?', ok: 'Yes'
                sh 'terraform apply -auto-approve tfplan'
            }
        }
    }

    post {
        success {
            echo 'Terraform pipeline executed successfully!'
        }
        failure {
            echo 'Terraform pipeline failed!'
        }
    }
}
