pipeline {
    agent any
    
    tools {
        nodejs 'Node18'
    }

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/soniakalonia/website.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build React App') {
            steps {
                sh 'npm run build'
            }
        }

        stage('Serve Build') {
            steps {
                sh '''
                npm install -g serve
                serve -s build -l 3000 &
                '''
            }
        }
    }
}