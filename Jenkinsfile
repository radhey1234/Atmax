            
pipeline {
    agent any
    
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                
            scp -o StrictHostKeyChecking=no -i singapurkey.pem singapurkey.pem ec2-user@3.0.61.215:/home/ec2-user/
                  // ssh -v -o StrictHostKeyChecking=no -i singapurkey.pem ec2-user@3.1.100.74 /bin/bash <mkdir /home/ec2-user/>
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

