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

    stage('Tests') {
      parallel {
        stage('Unit') {
          steps {
            sh 'dotnet test tests/UnitTests'
          }
        }

        stage('Integration') {
          steps {
            sh 'dotnet test tests/IntegrationTests'
          }
        }

        stage('Fontional') {
          steps {
            sh 'dotnet test tests/FunctionalTests'
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        sh 'dotnet publish eShopOnWeb.sln -o /var/aspnet'
        echo 'ÔK'
      }
    }

  }
}