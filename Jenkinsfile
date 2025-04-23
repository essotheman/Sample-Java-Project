pipeline{
    agent any 
    stages{
        stage('this code checkout'){
            steps{
                git 'https://github.com/essotheman/Sample-Java-Project.git'
            }
        }
        stage('this code compile'){
            steps{
                sh 'mvn compile' 
            }
        }
        stage('this code test'){
            steps{
                sh 'mvn test'
    
            }
        }
        stage('this code package'){
            steps{
                sh 'mvn clean package'
            }
        }
        stage('build docker image'){
            steps{
                sh 'cp /var/lib/jenkins/workspace/CI-CD-Pipeline/target/ABCtechnologies-1.0.war abc_tech.war'
                sh 'docker build -t theman764/abc:latest .'
            }
        }
        stage('Push Docker Image') {
            steps {
                // Push Docker image to DockerHub
                withDockerRegistry([credentialsId: "dockerhub-creds", url: ""]) {
                    sh 'docker push theman764/abc:latest'
                }
            }
        }

        stage('Deploy as container') {
            steps {
                // Deploy the Docker container locally
                sh 'docker run -itd -p 8081:8081 --name abcapp theman764/abc:latest'
            }
        }
    }

}
    
