pipeline{
    agent any
    stages{
        stage('checkout'){
            steps{ git url:"https://github.com/anishudupan-rns/tempv",branch:"master"}
        }
        stage('Build'){
            steps{ sh 'mvn clean package'}
        }
        stage('Test'){
            steps{sh 'mvn test'}
        }
    }
    post{
        always{
            junit 'target/surefire-reports/*.xml'
        }
    }
}