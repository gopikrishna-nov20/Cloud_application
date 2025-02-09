pipeline {
    agent any

    environment {
        DEST_DIR = 'C:\\Users\\Administrator\\Desktop\\cloup_application\\Cloud_application'
    }

    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/gopikrishna-nov20/Cloud_application.git'
            }
        }
        stage('Zip Index.js') {
            steps {
                zip zipFile: 'Lambda.zip', archive: true, dir: '.', includes: 'index.js'
            }
        }
        stage('Copy Files') {
            steps {
                bat "xcopy /y /s index.js ${DEST_DIR}"
                bat "xcopy /y /s main.tf ${DEST_DIR}"
                bat "xcopy /y /s sso.tf ${DEST_DIR}"
                bat "xcopy /y /s Lambda.zip ${DEST_DIR}"
            }
        }
        stage('Run Terraform') {
            steps {
                bat "cd ${DEST_DIR}"
                bat 'terraform init'
                bat 'terraform apply -auto-approve'
            }
        }
    }
}
