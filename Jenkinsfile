            
pipeline {
    agent any

    environment {
        AWS_ACCESS_KEY     = credentials('radhey-aws-cred')
        AWS_SECRET_KEY = credentials('radhey-aws-cred')
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
