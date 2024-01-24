pipeline {
	agent any

	tools {
		maven 'maven 3.6.1'
	}
	
	stages {
		stage("build") {
			when {
                		changeset "**/result/**"
 			 }	
		    	steps {
				echo 'Compiling result app..'
				dir('result') {
					npm 'install'
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
					npm 'install'
                    			npm 'test'
             
				}
			}
		}
	}
	
	post {
		always {
			echo 'Building multibranch pipeline for result is completed..'
		}
	}
}	


