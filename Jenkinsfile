pipeline {
    agent any

    stages {
        stage('Prepare') {
            steps {
                nodejs(nodeJSInstallationName: 'Node 22.x') {
                    sh 'npm config ls'
                }
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
