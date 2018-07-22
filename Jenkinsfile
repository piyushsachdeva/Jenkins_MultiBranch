pipeline {
    agent any
    environment {
    PATH = "/Users/himanichauhan/Documents/apache-maven-3.5.4/bin:$PATH"
                }
    stages{
        stage('Build'){
            steps {
                echo "$PATH"
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
