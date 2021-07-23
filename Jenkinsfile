pipeline {
	agent any
	stages { 
			stage('One') { 
						steps {
							sh ' echo "Step One" '
							script {
								def scannerhome= tool 'SonarQubeScanner';
								withSonarQubeEnv('MySonarQubeServer'){
								sh "${scannerhome}/bin/sonar-scanner \
  								-Dsonar.projectKey=my-app1 \
  								-Dsonar.sources=. \
  								-Dsonar.host.url=http://52.15.129.141:9000 \
  								-Dsonar.login=d95f7c9d6fac6bb6b797128d50fc2d5bae7a4c3c"
								
								}
								}
							}	
				     }		
		
				       
			}


