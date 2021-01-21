pipeline {
    agent any

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