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
        sh '''az login --service-principal -u \'70f1443e-39c2-4d41-bb25-fb53bf2f66d8\' -p \'16I8Q~mczScDfgTmyjbfi0pasuOPyHvuu~1X_aE9\' -t \'e89b9cb6-ceb6-41ac-8dcc-950ebbc47dae\'
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