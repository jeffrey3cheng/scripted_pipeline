pipeline {
   agent any

   stages {
      stage('Git-Checkout') {
         steps {
            echo 'Checking out from Git Repo'
            git 'https://github.com/jeffrey3cheng/scripted_pipeline.git'
         }
      }
      stage('Build it') {
         steps {
            echo 'Build it'
            sh label: '', script: 'sh Build.sh'
         }
      }      
      stage('UnitTest') {
         steps {
            echo 'Unit Test it'
            sh label: '', script: 'sh UnitTest.sh'
         }
      }
      stage('FuncTest') {
         steps {
            echo 'Functional Test'
            sh label: '', script: 'sh FuncTest.sh'
         }
      }     
      stage('Depoly') {
         steps {
            echo 'Deploy code'
            sh label: '', script: 'sh Deploy.sh'
         }
      }
   }
   post {
       always {
           echo "In Post, always"
       }
       success {
           echo "In Post, success"
       }
       failure {
           echo "In Post, failure"
       }
       unstable {
           echo "In Post, unstable"
       }
       changed {
           echo "In Post, change"
       }
    }
}
