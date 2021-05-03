pipeline{
     
     environment {
    imagename = "mulayam97/jenkins-docker-demo"
    registryCredential = 'docker-hub-credential'
    dockerImage = ''
}
     agent any
    tools{
        maven "maven3.8.1"
        dockerTool "docker"
       
      
    }
    stages{
        stage("Maven-build"){
            steps{
                sh "mvn --version"
                sh "mvn clean install"
            }
        }

        stage("Docker-Image-Build"){
            steps{
               
            script{
                dockerImage = docker.build imagename
            }
            }
        }
    }
    post{
        always{
            cleanWs()
        }
    }
}
