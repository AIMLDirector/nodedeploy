pipeline {
 
  stages {
    stage('Build') {
      steps {
        sh 'docker build -f "Dockerfile -t prem/nodejssys:latest .'
      }
    }
    stage('Publish') {
      when {
        branch 'master'
      }
      steps {
         withDockerRegistry(registry: [credentialsId: 'dockerhub']) {
          sh 'docker push prem/nodejssys:latest'
        }
      }
    }
  }
}

