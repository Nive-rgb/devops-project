pipeline {
     agent any

     stages {

          stage('Clone') {
               steps {
                   echo 'Cloning Repository'
               }
          }

          stage('Build Docker Image') {
              steps {
                   sh 'docker build -t devops-web .'
              }
          }

          stage('Deploy Container') {
              steps {
                   sh '''
                   docker rm -f devops-container || true
                   docker run -d -p 8081:80 --name devops-container devops-web
                   '''
               }
             }
          }
      }
