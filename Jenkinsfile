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
        emailext(subject: 'Approval Needed for Jenkins Build', body: 'Please click on the following link to approve the Jenkins build and proceed to the next job ${BUILD_URL}input/', from: 'prabhatbhadoriya07@gmail.com', mimeType: 'text/html', to: 'prabhat.bhadoriya@inspiritvision.com')
      }
    }

    stage('Deploy') {
      steps {
        sh 'echo "This is Deployment Stage"'
      }
    }

  }
}