pipeline{
    agent {
        label 'agent-node'
    }
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
                sh 'mvn package'
            }
        }
        
        }
}
    
