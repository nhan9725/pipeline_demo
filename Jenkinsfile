pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Buiding..'
                sh 'make' 
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true 
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh 'make check || true' 
                junit '**/target/*.xml'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                when {
              expression {
                currentBuild.result == null || currentBuild.result == 'SUCCESS' 
              }
            }
            steps {
                sh 'make publish'
            }
            }
        }
    }
}
