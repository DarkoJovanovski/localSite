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
        
        
        /*stage('artifact') {
            steps {
	    	// publish artifact to jfrog using curl command
		bat """curl -u admin:adminAdm1n -X PUT "http://localhost:8082/artifactory/example-repo-local/" -T C:\\test6.json"""
				
            }
        } */
	    
	/*stage('artifact2') {
            steps {
                def uploadSpec = """{
  			"files": [
			{
			"pattern": "C:\\test6.json",
      			"target": "http://localhost:8082/artifactory/artifactory-build-info/"
    			}
			]
	server.upload spec: uploadSpec
		}"""
		
            }
        } */
	    
	    
	 /*stage ('Upload file') {
            steps {
                rtUpload (
                    // Obtain an Artifactory server instance, defined in Jenkins --> Manage Jenkins --> Configure System:
		 def server = Artifactory.newServer """url: 'http://localhost:8082/artifactory/example-repo-local/', username: 'admin', password: 'adminAdm1n'""",
                 //serverId: example-repo-local,
		//def server = Artifactory.server 'example-repo-local',
			//def server = Artifactory.newServer url: 'http://localhost:8082/artifactory/example-repo-local/', credentialsId: '9dbbeffc-68e0-4814-a795-6efe04db745f',
               def uploadSpec = """{
                            "files": [
                                    {
                                        "pattern": "C:\\test7.json",
                                        "target": "http://localhost:8082/artifactory/example-repo-local/"
                                    }
                                ]
                            }"""
			server.upload spec: uploadSpec
                )
            }*/
	    	
	    stage ('upload artifact') {
	    	rtUpload (
    			serverId: 'example-repo-local/',
    			spec: '''{
          			"files": [
           			 {
             			 "pattern": "C:\\test7.json",
            			"target": "http://localhost:8082/artifactory/example-repo-local/"
           	 		}
         			]
    			}'''
		
		   )
	   
        }
	    
    }    
}
