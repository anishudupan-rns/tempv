pipeline{
    agent any
    stages{
        stage('checkout'){
            steps{ git url:"https://github.com/anishudupan-rns/tempv",branch:"master"}
        }
        stage('Test'){
            steps{ sh 'mvn clean test'}
        }
        stage('Build'){
            steps{sh 'mvn compile'}
        }
    }
    post{
        always{
            junit 'target/surefire-reports/*.jar'
        }
    }
}