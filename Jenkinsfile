node{
    
    stage('Clone') {
        checkout scm
    }
    stage('Terraform init') {
        sh 'terraform init'
    }
    stage('terraform apply') {
        sh 'terraform plan'
        sh 'terraform apply --auto-approve'
    }
}
