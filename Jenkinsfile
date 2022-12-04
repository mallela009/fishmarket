pipeline{
    agent any
    environment {
        PATH = "$PATH: /usr/share/maven/bin"
    }
    stages{
       stage('GetCode'){
            steps{
                git 'https://github.com/mallela009/fishmarket.git'
            }
       }       
       stage('Build'){
            steps{
                sh 'mvn clean package'
            }
         }
        stage('SonarQube analysis') {
 // def scannerHome = tool 'SonarQubeScanner-4.7.0';
        steps{
        withSonarQubeEnv('sonarqube- 9.7.1') { 
        // If you have configured more than one global server connection, you can specify its name
//      sh "${scannerHome}/bin/sonar-scanner"
        sh "mvn sonar:sonar"
    }
        }
        }
       
    }
}
