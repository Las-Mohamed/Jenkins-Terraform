node{
    agent any
    environment {
   AZURE = credentials('f2d10700-72b4-4064-b1d8-1a4882c4f29f')
}
     stage('Clone') {
        checkout scm
    }
    stage('Credentials') {
        sh 'az login --service-principal -u $AZURE_CLIENT_ID -p $AZURE_CLIENT_SECRET -t $AZURE_TENANT_ID'
    }
  
   /* withCredentials([azureServicePrincipal('f2d10700-72b4-4064-b1d8-1a4882c4f29f')]) {
    sh 'az login --service-principal -u $AZURE_CLIENT_ID -p $AZURE_CLIENT_SECRET -t $AZURE_TENANT_ID'
}*/
  /*  stage('az login') {     
            withCredentials([
                    azureServicePrincipal(credentialsId: 'f2d10700-72b4-4064-b1d8-1a4882c4f29f', AZURE_CLIENT_SECRET: 'TF_VAR_clientsecret', AZURE_CLIENT_ID: 'TF_VAR_clientid', AZURE_TENANT_ID: 'TF_VAR_tenantid', AZURE_SUBSCRIPTION_ID: 'TF_VAR_subscriptionid')
                ])
     }*/
    stage('terraform init') {     
            /*withCredentials([
                    azureServicePrincipal(credentialsId: 'f2d10700-72b4-4064-b1d8-1a4882c4f29f', AZURE_CLIENT_SECRET: 'TF_VAR_clientsecret', AZURE_CLIENT_ID: 'TF_VAR_clientid', AZURE_TENANT_ID: 'TF_VAR_tenantid', AZURE_SUBSCRIPTION_ID: 'TF_VAR_subscriptionid')
                ])*/
        sh 'terraform init -upgrade'
    }
    stage('terraform apply') {
        sh 'terraform apply -auto-approve'
    }
}
