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
        } stage("Docker-Image-build"){
            steps{
                sh "docker build -t spring-boot-docker ."
            }
        }

    }
    post{
        always{
            cleanWs()
        }
    }
}
