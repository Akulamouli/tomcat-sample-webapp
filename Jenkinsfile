pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'jar -cvf sample.war *'
            }
        }
        stage('Deploy') {
            steps {
                sh 'cp sample.war /home/ec2-user/tomcat/apache-tomcat-10.1.17/webapps/'
            }
        }
    }
	post {
			success {
				// Actions to perform on successful build
				echo 'Build and deployment successful!'
			}
			failure {
				// Actions to perform on build failure
				echo 'Build or deployment failed!'
			}
		}
}

