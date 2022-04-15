pipeline {
    agent any
    parameters {
        string(name: 'Greeting', defaultValue: 'Hello', description: 'How should I greet the world?')
    }
    
    
    stages {
        stage('Test') {
            steps {
                sh 'make check'
            }
        }
        
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
   post {
        always {
            junit '**/target/*.xml'
        }
        failure {
            mail to: team@example.com, subject: 'The Pipeline failed :('
        }
    }
    }
}
