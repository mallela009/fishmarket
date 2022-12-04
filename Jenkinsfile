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
                withSonarQubeEnv('SonarQubeScanner-4.7.0') {
                    // Optionally use a Maven environment you've configured already
                    withMaven(maven:' Maven 3.6.3') {
                        sh 'mvn clean package sonar:sonar'
                    }
                }
            }
        }
    }
        }
