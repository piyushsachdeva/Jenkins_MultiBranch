pipeline {
    agent any
    stages{
        stage('Build'){
            def mvn_version = '/Users/himanichauhan/Documents/apache-maven-3.5.4'
            withEnv( ["PATH+MAVEN=${tool mvn_version}/bin"] )
            steps {
                sh 'mvn clean package'
            }
            post {
                success {
                    echo "Now Archiving...!!"
                    archiveArctifacts artifacts: '**/target/*.war'
                }
            }
        }
    }
}
