pipeline {
   agent any
   environment {
       SERVER_CREDENTIALS = credentials('cred')
   }
   stages {
      stage('init') {
         steps {
            echo 'Initialising Phase'
            echo "Credentials are ${SERVER_CREDENTIALS}"
         }
      }
      stage('Compile') {
         steps {
            echo 'Compile Phase'
         }
      }
      stage('Build') {

         steps {
            echo 'Build Phase'
         }
      }
      stage('Run') {
         steps {
            echo 'Run Phase'
         }
      }
      stage('Unit') {
          when {
              expression {
                  env.BRANCH_NAME == 'dev' || env.BRANCH_NAME == 'master'
              }
          }
         steps {
            echo 'Unit Test Phase'
         }
      }
      stage('Integration') {
         steps {
            echo 'Integration Phase'
         }
      }
      stage('Deploy') {
         steps {
            echo 'Deployment Phase'
         }
      }
   }
   post {
       always {
           //run at all cost
           echo 'Run this execution at all cost'
       }
       success {
           //Run only when success
           echo 'We have a success build...Great!'
                  }
       failure {
           echo 'something went wrong...need to take corrective measures'
       }
   }
}
