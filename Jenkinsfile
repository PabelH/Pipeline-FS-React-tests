pipeline {
  agent any
  
  stages {
    stage('Clone repository') {
      steps {
        git 'https://github.com/PabelH/react-testing.git'
      }
    }
    stage('Install dep') {
      steps {
        
          sh 'npm install'
          
          //sh 'yarn test'
        
      }
    }
  stage('Testing') {
      steps {
    
        //  sh 'yarn test'
          sh 'npm run test'
        
      }
    }
  stage('Build and push Docker image') {
      steps {
        withAmazonEcrRegistry(credentialsId: 'ecr:us-east-2:aws-credentials') {

        sh 'docker build -t radionet .'
        sh 'docker tag radionet:latest 713860279714.dkr.ecr.us-east-2.amazonaws.com/radionet:latest'
        sh 'docker push 713860279714.dkr.ecr.us-east-2.amazonaws.com/radionet:latest'

        }
      }
    }  
  }
}