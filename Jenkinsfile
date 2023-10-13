pipeline {
  agent any
  stages {
    stage('test') {
      agent {
        node {
          label 'SlaveNode'
        }

      }
      steps {
        sh 'echo "hello this is first blue ocean pipeline"'
      }
    }

    stage('build') {
      steps {
        sh 'echo "This is Build Stage"'
      }
    }

    stage('Deploy') {
      steps {
        sh 'echo "This is Deployment Stage"'
      }
    }

  }
}