pipeline {
agent any


stages {

    stage('Build') {
        steps {
            echo 'Starting Maven Build...'
            sh 'mvn clean package'
            echo 'Build Completed'
        }
    }

    stage('Deploy') {
        steps {
            echo 'Deploy stage started'


            sh '''
            whoami
            pwd
            ls -l target/
            sudo cp target/*.war /opt/tomcat/webapps/
            sudo systemctl restart tomcat
            '''

            echo 'Deploy stage completed...'
            }

      }


}


}

