pipeline {
    agent{
        label "master"
    }
    tools{maven 'M3'}
    stages{
        stage('Checkout'){
            steps {
                git branch: 'main', 
                url: 'https://github.com/fegaris/SpringPetClinic.git'
            }
        }
        stage('Build'){
            steps {
                sh 'mvn compile'
            }
        }
        stage('Test'){
            steps {
                sh 'mvn test'
            }
        }
        stage('Package'){
            steps {
                sh 'mvn package'
            }
        }
        stage('Deploy'){
            steps{
                sh 'echo "$(pwd)"'
                sh 'java -jar target/*.jar'
            }
        }
    }
    
}
