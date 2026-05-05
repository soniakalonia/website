pipeline {
    agent any

    stages {

        stage('Clone Project') {
            steps {
                git 'C:/Users/abcom/website'
            }
        }

        stage('Deploy Website') {
            steps {
                bat '''
                echo Cleaning old files...
                rmdir /S /Q C:\\deploy\\website

                echo Creating deploy folder...
                mkdir C:\\deploy\\website

                echo Copying new files...
                xcopy /E /I /Y * C:\\deploy\\website
                '''
            }
        }

        stage('Deployment Done') {
            steps {
                echo 'Website deployed successfully!'
            }
        }
    }
}