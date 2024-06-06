pipeline {
    agent {
        node {
            label 'maven'
        }
    }
environment {
    PATH = "/opt/maven/bin:$PATH"
}
    stages {
        stage("build"){
            steps { 
                sh 'mvn clean deploy'
            }
        }

        // stage('SonarQube analysis') {
        //     environment {
        //         scannerHome = tool 's1prove-sonar-scanner'
        //     }
        //     steps{
        //         withSonarQubeEnv('s1prove-sonarqube-server') { // If you have configured more than one global server connection, you can specify its name
        //             sh "${scannerHome}/bin/sonar-scanner"
        //         }
        //     }
        // }
    }
}