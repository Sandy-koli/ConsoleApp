
def gv
pipeline {
   agent any
   
   stages {
      stage('init') {
         steps {            
            echo 'Init Phase'
         }
      }
      stage('Compile') {
         steps {
            echo 'Compile Phase'
         }
      }
      stage('Build') {

         steps {
            scripts {
               checkout scm
               gv = load "./script.groovy"
               gv.buildApp()
            }
         }
      }
      stage('Run') {
         steps {
            echo 'Run Phase'
         }
      }
      stage('Unit') {
         //  when {
         //      expression {
         //          env.BRANCH_NAME == 'dev' || env.BRANCH_NAME == 'master'
         //      }
         //  }
         steps {
            scripts {
               gv.UnitTestApp()
            }
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
            
            // withCredentials([usernamePassword(credentials: 'cred', usernameVariable: USER)])
            // {
            //    echo "User Name set is"
            //    //echo "Password set is ${PWD}"
            // }
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
