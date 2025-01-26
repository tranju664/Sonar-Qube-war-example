pipeline{
    agent {label 'jfrog'}
    stages{
       /*stage('Git Checkout Stage'){
            steps{
                git branch: 'main', url: 'https://github.com/tranju664/Sonar-Qube-war-example.git'
            }
         }*/       
       stage('Build Stage'){
            steps{
                sh 'mvn clean install'
            }
         }
       stage('SonarQube Analysis Stage') {
            steps{
                withSonarQubeEnv('sonardemo') { 
                    sh "mvn clean verify sonar:sonar -Dsonar.projectKey=sonardemo"
                }
            }
        }
    }
}
