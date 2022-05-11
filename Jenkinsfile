pipeline {
    agent any
	
    stages {
	    
	    stage('cmd') {
            steps {
                // build dotnet core app
                bat "ssh darko@192.168.2.90 'ls'"

            }

        }
	    
	/*   
        stage('Pull proj') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/DarkoJovanovski/localSite.git'

            }

        }
        
        stage('build') {
            steps {
                // build dotnet core app
                bat 'dotnet build --output C:\\.\\myLocalSite'

            }

        }
        
        
        stage('publish') {
            steps {
                // publish dotnet core app
                bat 'dotnet publish --output C:\\.\\myLocalSite'

            }
        }
	    
	stage('push the app to linux') {
            steps {
                bat 'scp -i C:\\Users\\darko.jovanovski\\.ssh\\id_rsa.pem -r C:\\Users\\darko.jovanovski\\Desktop\\myLocalSite darko@192.168.2.90:/home/darko'
            }
        }
	  */  
       /* stage ('zip the app') {
            steps {
                // bat 'mkdir archive'
                //bat 'echo test > archive/myLocalSite.txt'
                //zip zipFile: 'myLocalSite.zip', archive: false, dir: 'archive'
		zip zipFile: 'myLocalSite.zip', dir: '.'
                //archiveArtifacts artifacts: 'myLocalSite.zip', fingerprint: true
            }
	}
        
          
	 stage ('Upload file') {
            steps {
		    // deploying artifact. File mentioned in "pattern" is in worspace myLocalSite (whole path is in jenkins build)
		   script {	
               		def server = Artifactory.server "example-repo-local";
			   def uploadSpec = """{
                            	"files": [
                                    	{
                                       	"pattern": "myLocalSite.zip",
                                        "target": "example-repo-local"
                                    	}
                                	]
                            	}"""
			server.upload spec: uploadSpec	
		    }
	    }    
	 }*/
	        
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
