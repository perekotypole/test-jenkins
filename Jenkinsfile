pipeline {
    agent any

    tools {
        nodejs 'NodeJS_22'
    }

    stages {
        stage('Prepare') {
            steps {
                script {
                    def nodeInstallation = tool name: 'NodeJS_22', type: 'NodeJSInstallation'
                    env.PATH = "${nodeInstallation}/bin:${env.PATH}"
                }
		sh 'node -v'
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
