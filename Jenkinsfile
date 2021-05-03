pipeline{
     
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
            
               docker.build "test"
            }
        }
    }
    post{
        always{
            cleanWs()
        }
    }
}
