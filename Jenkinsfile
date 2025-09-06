pipeline {
  agent any
  stages {
    stage('terraform-version') {
      steps {
        sh '''terraform version
az version'''
      }
    }

    stage('azure-login') {
      steps {
        sh '''AZURE_CLIENT_ID=\'70f1443e-39c2-4d41-bb25-fb53bf2f66d8\'
AZURE_CLIENT_SECRET=\'16I8Q~mczScDfgTmyjbfi0pasuOPyHvuu~1X_aE9\'
AZURE_TENANT_ID=\'e89b9cb6-ceb6-41ac-8dcc-950ebbc47dae\'

az login --service-principal -u $AZURE_CLIENT_ID -p $AZURE_CLIENT_SECRET -t $AZURE_TENANT_ID
az account show'''
      }
    }

    stage('terraform-init') {
      steps {
        sh '''terraform init
terraform plan
terraform apply -auto-approve'''
      }
    }

  }
}