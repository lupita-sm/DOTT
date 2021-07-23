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
            sh """/var/lib/jenkins/tools/hudson.plugins.sonar.SonarRunnerInstallation/SonarQubeScanner \
           -D sonar.login=admin \
           -D sonar.password=admin \
           -D sonar.projectBaseDir=/var/lib/jenkins/workspace/neew \
           -D sonar.projectKey=my-app1 \
	   -D sonar.sources=cidr_convert_api/go \
	   -D sonar.host.url=http://52.15.129.141:9000/""",sudo: true
        }
        timeout(time: 10, unit: 'MINUTES') {
            waitForQualityGate abortPipeline: true
        }
    }
}             
}
}
}
