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

    stage('Approval') {
      steps {
        script {
          def recipient = 'prabhat.bhadoriya@inspiritvision.com'
          def buildUrl = "${JENKINS_URL}/job/${JOB_NAME}/build?token=TOKEN_FOR_BUILD"

          emailext(
            to: recipient,
            subject: 'Approval Needed for Jenkins Build',
            body: """
            <p>Dear User,</p>
            <p>Please click on the following link to approve the Jenkins build:</p>
            <p><a href='${buildUrl}'>Click here to approve</a></p>
            """,
            mimeType: 'text/html'
          )
        }

      }
    }

    stage('Deploy') {
      steps {
        sh 'echo "This is Deployment Stage"'
      }
    }

  }
}