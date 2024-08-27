pipeline {
    agent any

    tools{
        maven "mvn"
    }

    stages {
        stage('Git Checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'GitHub', url: 'https://github.com/rahultiple31/simple-java-maven-app-may-24.git']])
            }
        }

        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deploy on Ec-2'
            }
        }
    }
}
