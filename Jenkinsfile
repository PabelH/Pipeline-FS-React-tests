pipeline {
  agent any
  
  stages {
    stage('Clonar repositorio') {
      steps {
        git 'https://github.com/PabelH/react-testing.git'
      }
    }
    stage('Build') {
      steps {
        
          sh 'npm install'
          
          //sh 'yarn test'
        
      }
    }
  stage('Test') {
      steps {
          sh 'yarn install'
          sh 'yarn test'
        
      }
    }
  }
}