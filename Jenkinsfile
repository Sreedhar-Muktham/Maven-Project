pipeline {
    agent { label 'master' }
    tools {
        maven 'M2_HOME'
    }
    stages {
        stage ('Checkout') {
          steps {
            git 'https://github.com/Sreedhar-Muktham/Maven-Project.git'
          }
        }
        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }
        stage('Test'){
            steps {
                sh 'mvn test'
                junit '**/target/surefire-reports/TEST-*.xml'
            }
        }
        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
    }
}
