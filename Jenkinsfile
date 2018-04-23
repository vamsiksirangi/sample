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
             sh 'sudo docker build -t ubuntutom //home/vamsi/Vamsi/Docker/'
             sh 'sudo docker run -td --name ubuntutom -p 8180:8080 -v /var/lib/jenkins/workspace/myfirstpipeline/target/:/usr/local/tomcat/apache-tomcat-8.0.51/sample ubuntutom //bin/bash'
           }
         }  
    }
}
