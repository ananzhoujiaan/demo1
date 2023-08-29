pipeline {
  agent any
  stages {
    stage('Pull-Script') {
      steps {
        git(url: 'https://github.com/ananzhoujiaan/hello-world.git', branch: 'master')
      }
    }

    stage('Build') {
      steps {
        sh 'echo "Build"'
        sh 'docker build -t nginx:test .'
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