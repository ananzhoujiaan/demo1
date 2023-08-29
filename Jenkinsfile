pipeline {
  agent any
  stages {
    stage('Pull-Script') {
      steps {
        git(url: 'https://github.com/ananzhoujiaan/hello-world.git', branch: 'master')
      }
    }

    stage('Build') {
      environment {
        env = 'dev'
        tag = 'test'
      }
      steps {
        sh 'echo "Build"'
        sh 'echo "nginx:${tag}"'
      }
    }

    stage('Scan') {
      steps {
        sh 'echo "Scan"'
      }
    }

    stage('Harbor') {
      parallel {
        stage('Harbor') {
          steps {
            sh 'echo "harbor"'
          }
        }

        stage('config') {
          steps {
            sh 'echo "Get Config"'
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        sh 'echo "deploy"'
      }
    }

  }
  environment {
    env = 'dev'
    tag = 'test'
  }
}