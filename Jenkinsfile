pipeline{
    agent any
    
    stages{
       stage('Compile Stage'){
           
          steps {
              withMaven(maven : 'M2_HOME'){
                 sh 'mvn clean compile'
              }
          }
       }
      
       stage('Install stage'){
        
          steps{
              withMaven(maven : 'M2_HOME'){
                 sh 'mvn install'
              }
           }
       }
       
       stage('Creating  Docker Container'){
  
          steps{
             sh 'cd //home/vamsi/Vamsi/Docker'
             sh 'docker build -t ubuntutom //home/vamsi/Vamsi/Docker/Dockerfile'
             sh 'docker run -p 9900:8080 --name ubuntutom -v /var/lib/jenkins/workspace/myfirstpipeline/target/:/usr/local/tomcat/apache-tomcat-8.0.51/webapps -d ubuntutom //bin/bash'
           }
         }  
    }
}
