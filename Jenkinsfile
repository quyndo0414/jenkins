pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Stage Build"
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
    }    
}
