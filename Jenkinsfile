            
pipeline {
    agent any
    
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                
             ssh -i ec2-user@ec2-18.136.194.224:22:/home/ec2-user/
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

