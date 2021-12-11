            
pipeline {
    agent any

    environment {
        AWS_ACCESS_KEY     = credentials('AWS_ACCESS_KEY_ID')
        AWS_SECRET_KEY = credentials('AWS_SECRET_ACCESS_KEY')
    }

    stages {
        stage('Test') {
            steps {
                echo 'Testing..'
                echo $AWS_SECRET_KEY
                echo $AWS_ACCESS_KEY

            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh "npx serverless --no-aws-s3-accelerate --key $AWS_ACCESS_KEY --secret $AWS_SECRET_KEY"
            }
        }
    }
}
