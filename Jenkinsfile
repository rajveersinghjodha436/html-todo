pipeline {
    agent any

    environment {
        AWS_DEFAULT_REGION = 'ap-south-1'
        S3_BUCKET = 'first-demo-raj'
    }

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/rajveersinghjodha436/html-todo.git'
            }
        }

        stage('Deploy to S3') {
            steps {
                sh '''
                aws s3 sync . s3://$S3_BUCKET --delete
                '''
            }
        }
    }
}
