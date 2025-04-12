pipeline {
    agent any

    tools {
        nodejs 'NodeJS_22'
    }

    stages {
        stage('Prepare') {
            steps {
                sh'node -v'
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
