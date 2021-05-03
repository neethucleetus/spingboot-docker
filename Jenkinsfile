pipeline {
  environment {
    imagename = "mulayam97/jenkins-docker-demo"
    registryCredential = 'docker-hub-credential'
    dockerImage = ''
  }
  tools{
    dockerTool "docker"
  }
  agent any
  stages {
    
    stage('Building image') {
      steps{
        script {
          dockerImage = docker.build imagename
        }
      }
    }
    stage('Deploy Image') {
      steps{
        script {
          docker.withRegistry( '', registryCredential ) {
            dockerImage.push("$BUILD_NUMBER")
             dockerImage.push('latest')

          }
        }
      }
    }
    stage('Remove Unused docker image') {
      steps{
        sh "docker rmi $imagename:$BUILD_NUMBER"
         sh "docker rmi $imagename:latest"

      }
    }
  }
}
