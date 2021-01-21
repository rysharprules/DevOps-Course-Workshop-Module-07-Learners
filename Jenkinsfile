pipeline {
    agent none

    stages {
        stage('Build') {
            agent {
                docker { image 'mcr.microsoft.com/dotnet/sdk:3.1' }
            }
            steps {
                cd DotnetTemplate.Web
                dotnet build
            }
        }
        stage('dotnet Test') {
            agent {
                docker { image 'mcr.microsoft.com/dotnet/sdk:3.1' }
            }
            steps {
                cd DotnetTemplate.Web.Tests
                dotnet test
            }
        }
        stage('npm Test') {
            agent {
                docker { image 'node:14-alpine' }
            }
            steps {
                cd DotnetTemplate.Web
                npm -v
                npm i
                npm t
            }
        }
    }
}