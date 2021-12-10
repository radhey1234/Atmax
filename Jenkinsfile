            
pipeline {
    agent any
    
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                
                scp -o StrictHostKeyChecking=no -i "radhey123" ec2-user@3.1.100.74:/home/ec2-user/
               sudo ec2-user ssh ec2-user@3.1.100.74
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

