            
pipeline {
    agent any
    
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                 ssh -i ec2-user@13.213.4.95 
          //  scp -o StrictHostKeyChecking=no -i singapurkey.pem singapurkey.pem ec2-user@3.0.61.215:/home/ec2-user/
          //  ssh -i singapurkey.pem ec2-user@3.0.61.215 ls
                  //  echo "PATH = ${PATH}"
                 //   echo "GRADLE_HOME = ${GRADLE_HOME}"
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

