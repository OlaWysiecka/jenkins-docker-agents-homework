pipeline {
    agent {
        label 'docker-agent'
    }

    stages {
        stage('System information') {
            steps {
                echo 'Running on Docker agent...'

                sh 'echo "=== OS ==="'
                sh 'cat /etc/os-release'

                sh 'echo "=== Kernel ==="'
                sh 'uname -a'

                sh 'echo "=== User ==="'
                sh 'whoami'
            }
        }

        stage('Docker agent check') {
            steps {
                echo 'Docker agent is working correctly!'
                sh 'java -version'
            }
        }
    }

    post {
        success {
            echo 'Docker agent pipeline completed successfully.'
        }

        failure {
            echo 'Docker agent pipeline failed.'
        }

        always {
            echo 'Pipeline finished.'
        }
    }
}
