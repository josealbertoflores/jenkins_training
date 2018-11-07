pipeline {
  agent {
    dockerfile {
      filename 'Dockerfile'
    }

  }
  stages {
    stage('Build') {
      steps {
        echo 'Building...'
      }
    }
    stage('Test') {
      steps {
        echo 'Testing...'
      }
    }
    stage('Delivery') {
      steps {
        echo 'Delivering image to docker registry...'
        sh 'docker build -t $AWS_REGISTRY/$IMAGE_NAME:${env.BUILD_NUMBER} .'
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying...'
      }
    }
  }
  environment {
    IMAGE_NAME = 'charon_app'
    AWS_REGION = 'us-east-2'
    AWS_REGISTRY = '148039328980.dkr.ecr.us-east-2.amazonaws.com'
  }
}