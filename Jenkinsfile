pipeline {
    agent any
    
    stages {
        
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                    whoami
                '''
            }
        }

        stage ('Build') {
            steps {
                echo "Starting Build Process"
                sh 'pwd'
                sh './gradlew :bootJar'           
            }
        }
      
        
        stage ('copy') {
            steps {
                 
                 echo "Starting Copy"
            }
        }
        
        
        stage('Wait for user to input text?') {
                
            steps {
                    script {
                        echo "inside scripts"
                         def userInput = input(id: 'userInput', message: 'Merge to?',
                         parameters: [[$class: 'ChoiceParameterDefinition', defaultValue: 'strDef', 
                            description:'describing choices', name:'nameChoice', choices: "stage\nQA\nQA-Frontend"]
                         ])

                        println(userInput); //Use this value to branch to different logic if needed
                                    echo "The answer is: ${userInput}"

                        if( "${userInput}" == "stage"){
                            
                                  echo "Starting Copy"
                                  sh 'scp -o StrictHostKeyChecking=no build/libs/*.jar root@207.180.217.2:/opt/jenkins-practice-workspace'
                                  echo "Copy Done"
                            
                                  echo "starting stop tomcat"
                                  echo "${userInput}: server is starting"
                                  echo "Executing script to Stop"
                                  sh 'ssh root@207.180.217.2 /opt/stopScript.sh'
                                  echo "Stoped Server"
                                  
                                  echo "restarting the ${userInput}  server"
                                  echo "Executing script to start"
                                  sh 'nohup ssh root@207.180.217.2 /opt/startScript.sh'
                                  echo "started Server"
                        }
                        else if( "${userInput}" == "QA") {
                            echo "${userInput} : Starting Copy"
                            sh 'pwd'        
                            sh 'whoami'
                            
                            echo "Starting Copy"
                            sh 'scp -o StrictHostKeyChecking=no -i /var/jenkins_home/workspace/atmaxbackend.pem -T build/libs/*.jar ec2-user@13.235.49.151:/opt/'
                            echo "Copy Done"
                            
                            echo "Starting stop tomcat"
                            echo "Executing script to Stop"
                            sh 'ssh -o StrictHostKeyChecking=no  -i /var/jenkins_home/workspace/atmaxbackend.pem -T ec2-user@13.235.49.151  /opt/stopScript.sh'
                            echo "Stoped Server"
                            
                            echo "restarting ${userInput}  the server"
                            echo "Executing script to start"
                            sh 'ssh -o StrictHostKeyChecking=no  -i /var/jenkins_home/workspace/atmaxbackend.pem -T ec2-user@13.235.49.151 /opt/startScript.sh'
                            echo "started Server"

                            echo "${userInput} : Server Started"
                        }
                        else if( "${userInput}" == "QA-Frontend")
                            echo "${userInput} : Starting Copy"
                            
             }//Steps

        }//Stage 
      
      }

   }
}
