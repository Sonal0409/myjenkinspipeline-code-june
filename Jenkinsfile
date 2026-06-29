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
        stage('Code Quality Check'){
            steps{
              sh 'mvn pmd:pmd'
            }
            post{
                always{
                    echo 'Code Quality Check is completed'
                }
                success{
                    recordIssues sourceCodeRetention: 'LAST_BUILD', tools: [pmdParser(pattern: '**/pmd.xml')]
                }
                failure{
                    echo 'Code Quality Check is failed'
                }
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