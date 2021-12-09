            
pipeline {
    agent any
    
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                
               // scp -o StrictHostKeyChecking=no radhey123 ec2-user@18.136.194.224:22:/home/ec2-user/
               sudo -Hu ec2-user ssh ec2-user@18.136.194.224
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

