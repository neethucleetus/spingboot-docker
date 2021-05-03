pipeline{
    agent any
    tools{
        maven "maven3.8.1"
        docker "docker"
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
                docker.build docker-demo+":$BUILD_NUMBER"
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
