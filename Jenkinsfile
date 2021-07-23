pipeline {

    agent any 

    stages {
        stage('Checkout Codebase'){
            steps{
                checkout scm: [$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[credentialsId: 'github-ssh-key', url: 'git@github.com:lupita-sm/DOTT.git']]] 
            }
        }

        stage('Build') {
            steps {
                echo 'Building Codebase'
            }
        }

        stage('Test'){
            steps {
                echo 'Running Tests on changes'
            }
        }
        
        stage('Deploy'){
            steps{
                echo 'Done!'
            }
        }
    }

    post {

        always {
            echo 'Sending Slack message'
            sh "go run send-jenkins-notification/slack-notification.go ${BUILD_URL} ${currentBuild.currentResult} ${BUILD_NUMBER} ${JOB_NAME} "
        }
    }
}


https://binaries.sonarsource.com/Distribution/sonar-scanner-cli/sonar-scanner-cli-4.6.2.2472-linux.zip
