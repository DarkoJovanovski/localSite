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
                bat 'dotnet build --output .\\.\\myLocalSite'

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
	  
        stage ('zip the app') {
            steps {
                // bat 'mkdir archive'
                //bat 'echo test > archive/myLocalSite.txt'
                //zip zipFile: 'myLocalSite.zip', archive: false, dir: 'archive'
		zip zipFile: 'myLocalSite.zip', dir: '.'
                //archiveArtifacts artifacts: 'myLocalSite.zip', fingerprint: true
            }
	}
        
          
	    // deploying artifact. File mentioned in "pattern" is in worspace myLocalSite (whole path is in jenkins build)
	 stage ('Upload file') {
            steps {
		    
		   withCredentials([usernamePassword(credentialsId: '040a4186-05a6-4b58-adbf-0a04853e821d', passwordVariable: 'pass', usernameVariable: 'user')]) {

		    script {
			def server = Artifactory.newServer url: 'http://192.168.2.90:8082/artifactory/', username: "$user", password: "$pass"
			def uploadSpec = """{
                            "files": [
                                    	{
                                       	"pattern": "myLocalSite.zip",
                                        "target": "example-repo-local"
                                    	}
                                	]
                            	}"""
			server.upload spec: uploadSpec, failNoOp: true	
		    } 
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
    }    
}
