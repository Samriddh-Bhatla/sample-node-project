pipeline {
  agent any
  stages { 
    stage('Build Docker Image') { 
      steps { 
        script { 
          docker.build('nodeapp') 
        } 
      } 
    } 
    stage('Push Docker Image') { 
      steps { 
        script { 
          docker.withRegistry('http://localhost:5000', 'my-docker-repo-cred') { 
            docker.image('nodeapp').push() 
          } 
        } 
      } 
    }
  }
}
