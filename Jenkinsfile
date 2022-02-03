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
	    
        stage ('zip the app') {
            steps {
                bat 'mkdir archive'
                //bat 'echo test > archive/myLocalSite.txt'
                zip zipFile: 'myLocalSite.zip', archive: true, dir: 'archive'
                archiveArtifacts artifacts: 'myLocalSite.zip', fingerprint: true
            }
	}
        
       
	 /*   
	 stage ('Upload file') {
            steps {
		    // deploying artifact. File mentioned in "pattern" is in worspace myLocalSite (whole path is in jenkins build)
		   script {	
               		def server = Artifactory.server "example-repo-local";
			   def uploadSpec = """{
                            	"files": [
                                    	{
                                       	"pattern": "novtest1.json",
                                        "target": "example-repo-local"
                                    	}
                                	]
                            	}"""
			server.upload spec: uploadSpec	
		    }
	    }    
	 } */
	        
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
    }    
}
