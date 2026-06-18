pipeline{
agent any

 stages {

   stage('Checkout') {
     
	steps {
	    
	    git branch: 'main'
	    
 	    url: 'git@github.com:Ribe1/jenkins-pipeline.git'	        
         }
    }

    stage('Build') {

	steps {

	      sh 'mvn clean package'
	}
    }


     stage('Deploy') {
	
	steps {
         
            sh ''' 
	    
            cp target/*.war /opt/tomcat/webapps/
  
            sudo systemctl restart tomcat

            '''
	}     
     }	


 }

}
