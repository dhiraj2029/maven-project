pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'LocalMaven') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'LocalMaven') {
                    sh 'mvn test'
                }
            }
        }

        stage ('Package stage')
        {
            steps {
                        withMaven(maven : 'LocalMaven')
                        {
                            sh 'mvn package'
                        }            
        }
      
        }
        
        
        stage ('delploy on tomcat')
        {
            steps {
                    //withMaven(maven : 'LocalMaven'){
		    sshagent(['tomcat']){
			sh 'ssh root@13.232.136.207'
			sh  'echo shiraj'  
                       //sh 'sudo su'
		       //sh 'chmod 777 /var/lib/tomcat/webapps/'
                       //sh 'scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/pipeline/webapp/target/webapp.war /var/lib/tomcat/webapps/'
                 }
        }
        }
}
}
