pipeline {
    agent any
    environment {
    PATH = "/Users/himanichauhan/Documents/apache-maven-3.5.4/bin:$PATH"
                }
    stages{
        stage('Build'){
            steps {
                //source ~/.bash_profile
                echo "$PATH"
                sh 'mvn clean package'
            }
            post {
                success {
                    echo "Now Archiving...!!"
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
        stage('Deploy to staging'){
            steps {
                build job: 'deploy-to-staging'
            }
        }

        stage('Deploy to production'){
            steps{
                timeout(time:5, unit:days){
                input message: 'Deployment approved?'
            }
                build job: 'deploy-to-production'
            }
            post{
            success{
                echo "deployment success"
            }
            failure{
                echo "deployment failed"
            }
        }
    }
}
}
