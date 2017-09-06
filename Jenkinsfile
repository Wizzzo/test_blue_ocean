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
            sh 'echo "this is in parallel build"'
            
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
            sh 'curl https://graph.facebook.com/youtube?access_token=EAADuoZCJsjN8BAFJSkvlDD3N7QtelCR4Q4trman2yWubE4pFoCQVDTs7i7HPlomTri9pU6TGuhzrlpkm1Af5qK1ffGqTpqHqpZAwU52FH2U104gFZA8E7ZC1ZBSIy23YLCuoSfI2ZCIZAE929tF8hZCUEwZAuC10tHQ4ZD'
            
          },
          "Deploy 2": {
            echo 'this is a parallel message on the deploy step build'
            
          },
          "curl stackoverflow and write text file": {
            sh 'curl http://ori-load-balancer-1011545099.eu-west-1.elb.amazonaws.com/Boris_Beytza'
            writeFile(file: 'temp_file.txt', text: 'this is text', encoding: 'utf-8')
            
          }
        )
      }
    }
    stage('Post Deploy') {
      steps {
        parallel(
          "Post Deploy": {
            sleep 5
            mail(subject: 'Sub', body: 'this is test', cc: 'oriwiesel@gmail.com', from: 'ori.wiesel@automat-it.com')
            
          },
          "Post Deploy 2": {
            echo 'sleeping for 5 seconds while printing this message'
            
          },
          "print file to screen": {
            readFile(file: 'temp_file.txt', encoding: 'utf-8')
            
          },
          "last step": {
            sh 'echo hello'
            
          }
        )
      }
    }
  }
}