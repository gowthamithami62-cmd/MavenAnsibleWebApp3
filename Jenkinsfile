pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy') {
            steps {
                sh 'cp target/*.war /home/shruthi/apache-tomcat-9.0.89/webapps/'
            }
        }

        stage('Restart Tomcat') {
            steps {
                sh '/home/shruthi/apache-tomcat-9.0.89/bin/shutdown.sh || true'
                sh '/home/shruthi/apache-tomcat-9.0.89/bin/startup.sh'
            }
        }
    }
}
