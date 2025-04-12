pipeline {
    agent any

    stages {
        stage('Prepare') {
            steps {
                sh '''
		    curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
		    sudo apt-get indtall -y nodejs
		    node -v
		'''
            }
        }

        stage('Build') {
            steps {
                sh 'npm --version'
            }
        }

        stage('Test') {
            steps {
                sh 'echo "JENKINS_URL: $JENKINS_URL"'
		sh 'node index.js'
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution completed.'
        }
    }
}
