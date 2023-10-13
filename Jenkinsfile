pipeline {
  agent {
    node {
      label 'SlaveNode'
    }

  }
  stages {
    stage('test') {
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