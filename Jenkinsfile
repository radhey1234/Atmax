@Library('github.com/releaseworks/jenkinslib') _     
pipeline {
    agent any

    environment {
        AWS_ACCESS_KEY     = credentials('Radhey')
        AWS_SECRET_KEY = credentials('Radhey')
    }

    stages {
        stage('Test') {
            steps {
                        withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: 'aws-key', usernameVariable: 'AWS_ACCESS_KEY_ID', passwordVariable: 'AWS_SECRET_ACCESS_KEY']]) {
        AWS("--region=ap-southeast-1 s3 ls")
    }
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
