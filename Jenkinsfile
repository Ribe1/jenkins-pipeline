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
            echo 'Starting Deployment...'

            sh '''
            cp target/*.war /opt/tomcat/webapps/
            sudo systemctl restart tomcat
            '''

            echo 'Deployment Completed'
        }
    }
}


}

