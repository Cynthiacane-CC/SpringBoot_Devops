pipeline {
   agent any
   
   tools {
     maven 'M2_HOME'
   }   
   stages {
     stage ('Git clone') {
        steps {
          echo 'clone GIt repo'
	  git branch: 'main', url: 'https://github.com/Cynthiacane-CC/devops-code1.git'

	          }
     
            }

	   
     stage ('Build') {
        steps {
          echo 'build step'
	  sh 'mvn clean install package' 

	          }
     
           }

 stage ('Test') {
        steps {
          echo "test step"
          sh 'mvn test'
              }

           }

 stage ('Deploy_Tomcat') {
        steps {
          echo "deploy to tomcat"
          deploy adapters: [tomcat8(credentialsId: 'TomcatUserID', path: '', url: 'http://3.83.143.92:8080/')], contextPath: null, war: '**/*.war'
         }

     }
   }
}