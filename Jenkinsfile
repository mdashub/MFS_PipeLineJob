pipeline {
    agent any

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
    }
}
