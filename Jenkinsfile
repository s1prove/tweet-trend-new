pipeline {
    agent {
        node {
            label 'maven'
        }
    }

environment {
    PATH = "/opt/apache-maven-3.9.8/bin:$PATH"
}

    stages {
        stage('build'){
            steps {
                sh 'mvn clean deploy'
            }
        }
        
        stage('SCM') {
            steps {
                git 'https://github.com/foo/bar.git'
            }
        }
        
        stage('SonarQube analysis') {
            environment {
                scannerHome = tool 'sonnar-scanner';
            }
            steps {
                withSonarQubeEnv('sonarqube-server') 
                { // If you have configured more than one global server connection, you can specify its name1
                    sh "${scannerHome}/bin/sonar-scanner"
                }
            }
        }
    }
}