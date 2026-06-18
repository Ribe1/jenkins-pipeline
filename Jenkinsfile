
pipeline{
  agent any

        stages {

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
	               
                       echo 'Deployment completed'

                       }     
              
              }	

             


  }

}
