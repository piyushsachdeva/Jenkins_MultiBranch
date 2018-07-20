pipeline {
    agent any
    tools{
        maven 'localMaven'
    }
    stages{
        stage('Build'){
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
