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
    }
}