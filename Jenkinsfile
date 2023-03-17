pipeline {
    agent any
    stages {
        stage('Build and Push Docker Image') {
            steps {
                withEnv(['env.test']) {
                    script {
                        sh """aws ecr get-login-password --region ${AWS_DEFAULT_REGION} | docker login --username AWS --password-stdin ${AWS_ACCOUNT_ID}.dkr.ecr.${AWS_DEFAULT_REGION}.amazonaws.com"""
                        sh "docker build -t ${IMAGE_REPO_NAME}:${IMAGE_TAG} ."
                        sh "docker tag ${IMAGE_REPO_NAME}:${IMAGE_TAG} ${REPOSITORY_URI}:${IMAGE_TAG}"
                        sh "docker push ${REPOSITORY_URI}:${IMAGE_TAG}"
                    }
                }
            }
        }
    }
}
