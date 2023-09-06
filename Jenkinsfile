pipeline{
    agent any
    environment {
        PATH = "$PATH:/opt/apache-maven-3.9.4/bin"
    }
    stages{
       stage('GetCode'){
            steps{
                git 'https://github.com/ravdy/javaloginapp.git'
            }
         }        
       stage('Build'){
            steps{
                sh 'mvn clean package'
            }
         }
        stage('SonarQube analysis') {
//    def scannerHome = tool 'SonarScanner 4.0';
        steps{
        withSonarQubeEnv('my-sonar-server') { 
        // If you have configured more than one global server connection, you can specify its name
//      sh "${scannerHome}/bin/sonar-scanner"
        sh "mvn sonar:sonar"
    }
        }
        }
       
    }
}
