pipeline {
  agent any
  stages {
    stage('fist-step') {
      steps {
        sh 'whoami'
      }
    }

    stage('Build') {
      steps {
        sh 'dotnet build eShopOnWeb.sln'
      }
    }

  }
}