pipeline{
    agent any   // current server where jenkins is running
    tools{
        maven 'mymaven'
    }
    stages{
        stage('Checkout the Code'){
            steps{
                git 'https://github.com/Sonal0409/DevOpsCodeDemo.git'
            }
        }
        stage('Compile the code'){
            steps{
                sh 'mvn compile'
            }
        }
        stage('Run Unit Tests'){
            steps{
                sh 'mvn test'
            }
        }
        stage('Build the code'){
            steps{
                sh 'mvn package'
            }
        }
    }
}