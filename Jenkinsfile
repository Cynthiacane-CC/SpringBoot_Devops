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
   }
}