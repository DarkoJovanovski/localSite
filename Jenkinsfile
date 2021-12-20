pipeline {
    agent any

    stages {
        /*stage('Pull proj') {
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

        }*/
        
        stage('Build') {
            steps {
				// set the nuget api user/pass for artifactory
                withCredentials(
                    [usernamePassword(
                        //credentialsId: 'admin', 
                        passwordVariable: 'adminAdm1n', 
                        usernameVariable: 'admin')]) {
                    
                    curl -u admin:adminAdm1n -X PUT "http://localhost:8082/artifactory/example-repo-local/" -T Desktop/proba2.json
					//bat """nuget restore -source https://wowinc.jfrog.io/wowinc/api/nuget/nuget/"""
					//bat """nuget restore"""
					//bat """msbuild $WORKSPACE\\${solution_location} /p:OutDir=$WORKSPACE\\Deploy\\,Configuration=${params.environment}"""
				}
            }
        } 
    }    
}
