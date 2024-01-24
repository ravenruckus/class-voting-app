pipeline {
	agent any

	tools {
		nodejs 'NodeJS 19.0.1'
	}
	
	stages {
		stage("build") {
			when {
                		changeset "**/result/**"
 			 }	
		    	steps {
				echo 'Compiling result app..'
				dir('result') {
					sh 'npm install'
				}
			}
		}
		stage("test") {
            		when {
                		changeset "**/result/**"
           		 }
			steps {
				echo 'Running Unit Tests on result app..'
				dir('result') {
					sh 'npm install'
                    			sh 'npm test'
             
				}
			}
		}
	}
	
}	


