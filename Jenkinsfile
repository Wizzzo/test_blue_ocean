pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        parallel(
          "Build": {
            echo 'Building..'
            
          },
          "Build 2": {
            sh 'echo "the is in parallel build"'
            
          }
        )
      }
    }
    stage('Test') {
      steps {
        parallel(
          "Test": {
            echo 'Testing..'
            
          },
          "Test 2": {
            echo 'thats is a a new message on the test step'
            
          }
        )
      }
    }
    stage('Deploy') {
      steps {
        parallel(
          "Deploy": {
            echo 'Deploying....'
            
          },
          "Deploy 2": {
            echo 'this is a parallel message on the deploy step build'
            
          }
        )
      }
    }
    stage('Post Deploy') {
      steps {
        parallel(
          "Post Deploy": {
            sleep 5
            
          },
          "Post Deploy 2": {
            echo 'sleeping for 5 seconds while printing this message'
            
          }
        )
      }
    }
  }
}