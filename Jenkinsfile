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

	    
	    /*stage ('server connection') {
            steps {
		   script {
			//def server = Artifactory.newServer """url: 'http://localhost:8082/artifactory/example-repo-local/', username: 'admin', password: 'adminAdm1n'"""	
               		def server = Artifactory.server 'example-repo-local'
		    }
	    }    
	 }*/
	    
	 stage ('Upload file') {
            steps {
		   script {	
               		def server = Artifactory.server "example-repo-local";
			   def uploadSpec = """{
                            	"files": [
                                    	{
                                       	"pattern": "appsettings.json",
                                        "target": "http://localhost:8082/artifactory/example-repo-local/"
                                    	}
                                	]
                            	}"""
			server.upload spec: uploadSpec	
		    }
	    }    
	 }
	    
	    
	    /*stage ('test string') {
		    steps {
			    script {
			    	def novString = "darko go vladej jenkins";
				String[] str;
				str = novString.split(' ');

				for( String values : str ){
					if (values.contains("jenkins")) 
					println(values);
				}    
			    }
		    }
	    }*/
	    
	    
	  /*  
	stage ('upload artifact') {
	  steps{
	    rtUpload (
    	      serverId: "example-repo-local",
    		spec: """{
          	  "files": [
			   {
             		     "pattern": "C:\\test7.json",
            		     "target": "http://localhost:8082/artifactory/example-repo-local/"
           	 	   }  
         	  ]
    		}"""
	    )
	  }
        }*/    
    }    
}
