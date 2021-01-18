pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage("Stage with input") {
           steps {
             script {
             timeout(time: 15, unit: "MINUTES") {
             input message: 'Do you want to approve the deploy in production?', ok: 'Yes'
             }
             }
           }
        }  
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
