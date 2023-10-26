 pipeline {
    agent any

    environment {
        GITHUB_REPO_URL = 'https://github.com/salma-al47/micro.git'
    }

    stages {
        stage('Checkout') {
            steps {
                script {
                    checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], userRemoteConfigs: [[url: GITHUB_REPO_URL]]])
                }
            }
        }
        stage('Build') {
            steps {
               sh 'docker build -t app -f api/Dockerfile .'
               sh 'docker build -t client -f client/Dockerfile .'
            }
        }
    }

    
