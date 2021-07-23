pipeline {
    agent any
        stages {
            stage('Build') {
                steps {
                    sh 'echo "Step One build something else" '
                }
            }
            stage('SonarQube') {
                steps {
                    sh 'echo "Step Two Sonar x" '
                }
            } 

            stage('Testing') {
                steps {
                    sh 'echo "Step Three ddd" '
                }
            }

            stage('Deploy') {
                steps {
                    sh 'echo "Step Three" '
                }
            }
           stage('Sonarqube') {
steps {
script {
       def scannerHome = tool "SonarQubeScanner";
        withSonarQubeEnv('MySonarQubeServer') {
		sh """${scannerhome}/bin/SonarQubeScanner\
  -Dsonar.projectKey=DOTT \
  -Dsonar.sources=. \
  -Dsonar.host.url=http://52.15.129.141:9000 \
  -Dsonar.login=d95f7c9d6fac6bb6b797128d50fc2d5bae7a4c3c
        }
        timeout(time: 10, unit: 'MINUTES') {
            waitForQualityGate abortPipeline: true
        }
    }
}             
}
}
}
