pipeline {
    agent any
	environment {
        NAME = 'Quy Do'
    }
    stages {
        stage('Build') {
            steps {
                echo "Stage Build"
		printenv NAME
            }
        }
        stage('Deploy') {
            steps {
                retry(3) {
                    echo "Stage Deploy"
                }
                timeout(time: 3, unit: 'MINUTES') {
                    echo "Health Check"
                }
            }
        }   
		stage('Test') {
            steps {
                echo "Test"
            }
        }
	}	
	post {
		always {
			echo 'This will always run'
		}
		success {
			echo 'This will run only if successful'
		}
		failure {
			echo 'This will run only if failed'
		}
		unstable {
			echo 'This will run only if the run was marked as unstable'
		}
		changed {
			echo 'This will run only if the state of the Pipeline has changed'
			echo 'For example, if the Pipeline was previously failing but is now successful'
		}
	}	    
}
