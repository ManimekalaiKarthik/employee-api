pipeline {

  agent any
 
  stages {
    stage('Build') {
      steps {
            bat 'mvn -B -U -e -V clean -DskipTests'
      }
    }

    stage('Test') {
      steps {
          bat "***********Munit test case execution*************"
      }
    }

     stage('Deployment') {
    	steps {
            bat 'mvn -U -V -e -B -DskipTests deploy -DmuleDeploy'
      }
    }
    
  }
}