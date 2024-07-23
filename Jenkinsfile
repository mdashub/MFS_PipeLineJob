pipeline {
    agent any

environment {
        RECIPIENTS = 'infinityloves49@gmail.com'
    }

    
    stages {
        stage('Trigger FreeStyleProject1') {
            steps {
                build job: 'FreeStyleProject1'
            }
        }
        stage('Trigger FreeStyleProject2') {
            steps {
                build job: 'FreeStyleProject2'
            }
        }
        stage('Trigger FreeStyleProject3') {
            steps {
                build job: 'FreeStyleProject3'
            }
        }

        stage('Trigger AmazonFloraTest1') {
            steps {
                build job: 'AmazonFloraTest1'
            }
        }
    }

     post {
        always {
            echo 'Cleaning up...'
            cleanWs() 
          
        }

          unstable {
            echo 'Pipeline succeeded!'
             emailext(
                to: "${RECIPIENTS}",
                subject: "SUCCESS: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
                body: "The job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' has UNSTABLE. Check details at: ${env.BUILD_URL}"
            )
        }
        success {
            echo 'Pipeline succeeded!'
             emailext(
                to: "${RECIPIENTS}",
                subject: "SUCCESS: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
                body: "The job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' has SUCCEEDED. Check details at: ${env.BUILD_URL}"
            )
        }
        failure {
            echo 'Pipeline failed!'
             emailext(
                to: "${RECIPIENTS}",
                subject: "SUCCESS: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
                body: "The job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' has FAILED. Check details at: ${env.BUILD_URL}"
            )
        }
    }
}
