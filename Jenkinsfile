pipeline {
    agent any

    stages {
        stage('Pull proj') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/DarkoJovanovski/localSite.git'

            }

        }
        
        stage('build') {
            steps {
                // build dotnet core app
                bat 'dotnet build --output C:\\Users\\darko.jovanovski\\Desktop\\myLocalSite'

            }

        }
        
        
        stage('publish') {
            steps {
                // publish dotnet core app
                bat 'dotnet publish --output C:\\Users\\darko.jovanovski\\Desktop\\myLocalSite'

            }

        }
        
    }
}
