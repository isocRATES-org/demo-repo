pipeline {
    agent any
    environment {
        PATH = "$PATH:/opt/apache-maven-3.9.4/bin"
    }
    stages {
        stage('GetCode') {
            steps {
                // Checkout the code from the Git repository
                git 'https://github.com/isocRATES-org/demo-repo.git'
            }
        }
        stage('Build') {
            steps {
                // Build your project using Maven
                sh 'mvn clean package'
            }
        }
        stage('SonarQube analysis') {
            steps {
                script {
                   // def scannerHome = tool name: 'SonarScanner 4.0', type: 'hudson.plugins.sonar.SonarRunnerInstallation'
                    withSonarQubeEnv('my-sonar-server') {
                        sh "${scannerHome}/bin/sonar-scanner"
                    }
                }
            }
        }
    }
}
