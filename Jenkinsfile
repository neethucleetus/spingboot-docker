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
               
              sh  "docker build -t jenkins-deocker-demo ."
            }
        }
    }
    post{
        always{
            cleanWs()
        }
    }
}
