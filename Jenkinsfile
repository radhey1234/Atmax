            
pipeline {
    agent any
    
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                
ssh -i "singapurkey.pem" ec2-user@ec2-18-136-194-224.ap-southeast-1.compute.amazonaws.com
                    echo "PATH = ${PATH}"
                    echo "GRADLE_HOME = ${GRADLE_HOME}"
                    echo "radhey radhey"
                '''
            }
        }

        stage ('Build') {
            steps {
                sh 'gradle' 
            }
        }
    }
}

