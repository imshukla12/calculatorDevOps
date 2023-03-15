pipeline {
    agent any
    stages {
        stage('Clone Git') {
            steps {
                git url: 'https://github.com/imshukla12/calculatorDevOps.git' , branch: 'main'
            }
        }
      stage('Maven Build') {
            steps {
                sh 'mvn clean install'
            }
        }
      stage('Docker Build to Image') {
             steps {
                  script{
                          imageName=docker.build "akanksha/calculator"
                   }
            }
        }
    }
}