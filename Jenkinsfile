pipeline {
    agent {
        docker { image 'mcr.microsoft.com/dotnet/sdk:3.1' }
    }

    stages {
        stage('Build') {
            steps {
                cd DotnetTemplate.Web
                dotnet build
            }
        }
        stage('dotnet Test') {
            steps {
                cd DotnetTemplate.Web.Tests
                dotnet test
            }
        }
        stage('npm Test') {
            steps {
                cd DotnetTemplate.Web
                npm i
                npm t
                npm run lint
            }
        }
    }
}