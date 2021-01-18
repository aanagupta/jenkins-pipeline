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
           def userInput = false
           script {
              def userInput = input(id: 'Proceed1', message: 'Promote build?', parameters: [[$class: 'BooleanParameterDefinition', defaultValue:true, description: '', name: 'Please confirm you agree with this']])
              echo 'userInput: ' + userInput

             if(userInput == true) {
                echo "This is true"
              } else {
                // not do action
                echo "Action was aborted."
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
