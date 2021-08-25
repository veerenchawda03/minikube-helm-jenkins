pipeline {
  agent {
    docker {
      image 'docker:20.10'
    }

  }
  stages {
    stage('Git clone') {
      steps {
        git(url: 'https://github.com/veerenchawda03/minikube-helm-jenkins.git', branch: 'main', credentialsId: '0b3f05d2-f5f7-4827-96bc-890ddff5acd3')
      }
    }

    stage('Docker build') {
      steps {
        sh 'docker build -t veeren03/fastapi:latest .'
      }
    }

    stage('Docker push') {
      steps {
        sh 'docker push veeren03/fastapi03:latest'
      }
    }

    stage('Helm upgrade') {
      steps {
        sh 'helm upgrade release1 minikube-test'
      }
    }

  }
}