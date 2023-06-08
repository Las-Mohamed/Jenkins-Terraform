node{
    
    stage('Clone') {
        checkout scm
    }
    withCredentials([azureServicePrincipal('credentials_id')]) {
    sh 'az login --service-principal -u $AZURE_CLIENT_ID -p $AZURE_CLIENT_SECRET -t $AZURE_TENANT_ID'
}
    stage('Terraform init') {
        sh 'terraform init'
    }
    stage('terraform apply') {
        sh 'terraform plan'
        sh 'terraform apply --auto-approve'
    }
}
