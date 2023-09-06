pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout your source code here if not already done
                // For example:
                checkout scm
            }
        }

        stage('SonarQube Analysis') {
            steps {
                script {
                    def scannerHome = tool name: 'my-sonar-server', type: 'hudson.plugins.sonar.SonarRunnerInstallation'
                    withSonarQubeEnv('http://18.232.77.236:9000') {
                        sh "${scannerHome}/bin/sonar-scanner"
                    }
                }
            }
        }

        // Add more stages as needed for your build and deployment process
    }

    post {
        success {
            // Actions to take when the pipeline succeeds
            echo 'Pipeline succeeded!'
            // You can add more actions here
        }
        failure {
            // Actions to take when the pipeline fails
            echo 'Pipeline failed!'
            // You can add more actions here
        }
    }
}
