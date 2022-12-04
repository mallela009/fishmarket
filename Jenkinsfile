pipeline {
    agent any
    stages {
        stage('SCM') {
            steps {
                git url: 'https://github.com/mallela009/fishmarket.git'
            }
        }
        stage('build && SonarQube analysis') {
            steps {
                withSonarQubeEnv('sonarqube-9.7.1') {
                    // Optionally use a Maven environment you've configured already
                    withMaven(maven:'Maven 3.5') {
                        sh 'mvn clean package sonar:sonar'
                    }
                }
            }
        }
    }
}
