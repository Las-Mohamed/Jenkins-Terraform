node{
    
    stage('Clone') {
        checkout scm
    }
    withCredentials([azureServicePrincipal('f2d10700-72b4-4064-b1d8-1a4882c4f29f')]) {
    sh 'az login --service-principal -u $AZURE_CLIENT_ID -p $AZURE_CLIENT_SECRET -t $AZURE_TENANT_ID'
}
    stage('Terraform init') {
        sh 'terraform init'
    }
    stage('terraform apply') {
        sh 'terraform apply --auto-approve'
    }
}
