pipeline {
    agent any
    parameters {
        string(name: 'Greeting', defaultValue: 'Hello', description: 'How should I greet the world?')
    }
    
    
    stages {      
        stage('Example') {
            steps {
                echo "${params.Greeting} World!"
            }
        }
        stage('Build') {
            steps {
                echo 'Buiding..'
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
