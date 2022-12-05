pipeline {
    agent any
    stages {
        stage('SCM') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-jenkins', url: 'https://github.com/mallela009/fishmarket.git']]])
            }
        }
       stage('Static Code Analysis'){
 sh 'mvn clean verify sonar:sonar -Dsonar.projectName=p1
 -Dsonar.projectKey=p1 -
Dsonar.projectVersion=$sonarqube-9.7.1';

    }
}
