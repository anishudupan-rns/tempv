pipeline{
    agent any
    parameters{
        string(name:'BRANCH_NAME',defaultValue:'master',description:'branch name to build')
    }
    stages{
        stage('checkout'){
            steps{ git url:'https://github.com/anishudupan-rns/tempv',branch:params.BRANCH_NAME }
        }
        stage('Build'){
            steps { sh 'mvn clean package' }
        }
        stage('Test'){
            steps { sh 'mvn test' }
        }
    }
    post{
        success{
            archiveArtifacts artifacts: 'target/*.jar'
        }
    }
}