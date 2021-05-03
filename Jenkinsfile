pipeline{
    agent any
    tools{
        maven "maven3.8.1"
        tool name: 'docker', type: 'dockerTool'
      
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
                sh "docker build -t jenkins-docker-demo ."
            }
        }
    }
    post{
        always{
            cleanWs()
        }
    }
}
