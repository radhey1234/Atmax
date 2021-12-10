            
pipeline {
    agent any
    
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                mssh i-09ed55d716b984fd5
            scp -i singapurkey.pem singapurkey.pem ec2-user@3.0.61.215:/home/ec2-user/
                  // ssh -v -o StrictHostKeyChecking=no ec2-user@3.1.100.74 /bin/bash
                   // echo "PATH = ${PATH}"
                  //  echo "GRADLE_HOME = ${GRADLE_HOME}"
                 //   echo "radhey radhey"
                '''
            }
        }

        stage ('Build') {
            steps {
                sh '''
                echo "radhey"
                '''
            }
        }
    }
}

