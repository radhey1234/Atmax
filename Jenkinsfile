
pipeline {
    agent any
    
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
            }
        }

        stage ('Build') {
            steps {
                sh 'mvn -Dmaven.test.failure.ignore=true install' 
                deploy adapters: [tomcat8(credentialsId: '945dc348-75c7-4b0c-8f59-452968106c46', path: '', url: 'http://54.255.223.23:8080/')], contextPath: null, war: '**/*.war'
            }
        }
    }
}
