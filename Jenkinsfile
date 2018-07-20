pipeline{
    agent any
    stages{
        stage('build'){
            steps {
                sh 'mvn clean package'

            }
            post {
                success {
                    echo "Now Archiving..!!"
                    archiveArctifacts artifacts: '**/target/*.war'
                }
            }
        }
    }
}
