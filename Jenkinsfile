pipeline {
    agent any
    parameters {
        string(name: 'Greeting', defaultValue: 'Hello', description: 'How should I greet the world?')
    }
    stage('Example') {
            steps {
                echo "${params.Greeting} World!"
            }
        }
    
    stages {
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
