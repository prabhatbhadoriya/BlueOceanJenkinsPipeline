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
          def approval = input(
            id: 'userInput',
            message: 'Do you want to continue?',
            parameters: [choice(choices: 'Approve', description: 'Click "Approve" to continue', name: 'Approval')]
          )

          if (approval == 'Approve') {
            echo 'Proceeding with the next job...'
          } else {
            error 'Build aborted by user'
          }
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