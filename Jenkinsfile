pipeline{
    agent any
    tools{
        maven "maven3.8.1"
    }
    stages{
        stage("Maven-build"){
            steps{
                sh "mvn --version"
                sh "mvn clean install"
            }
        }
        stage("Docker-Image-Build"){
            script{
                docker.build docker-demo+":$BUILD_NUMBER"
            }
        }
    }
    post{
        always{
            cleanWs()
        }
    }
}
