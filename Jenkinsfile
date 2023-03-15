pipeline {
    agent any
    stages {
        stage('Clone Git') {
            steps {
                git url: 'https://github.com/imshukla12/calculatorDevOps.git' , branch: 'master'
            }
        }
      stage('Maven Build') {
            steps {
                sh 'mvn clean install'
            }
        }
      stage('Docker Build to Image') {
             steps {
                  sh 'docker build -t imshukla/calculator:latest .'
            }
        }
      stage('Push Docker Image to Docker Hub') {
              steps {
                        withDockerRegistry([ credentialsId: "docker-cred", url: "" ]){
                        sh 'docker push imshukla/calculator:latest'
                    }
              }
      }
    }
}
