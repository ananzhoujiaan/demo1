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
      }
    }

    stage('Scan') {
      steps {
        sh 'echo "Scan"'
      }
    }

    stage('get config') {
      steps {
        sh 'echo "config"'
      }
    }

    stage('deploy') {
      steps {
        sh 'echo "deploy"'
      }
    }

  }
}