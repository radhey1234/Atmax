
pipeline {
    agent {label 'Jenkins-Slave'}
    
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "radhey"
                    echo "PATH = ${PATH}"
                    echo "GRADLE_HOME = ${GRADLE_HOME}"
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
