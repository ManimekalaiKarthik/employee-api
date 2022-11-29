pipeline {

  agent any
  
  environment{
    ANYPOINT_CREDS = Credentials('ANYPOINT_CREDENTIALS')
    }
 
  stages {
    stage('Build') {
      steps {
            bat 'mvn -B -U -e -V clean -DskipTests'
      }
    }

    stage('Test') {
      steps {
          echo "***********Munit test case execution*************"
      }
    }

     stage('Deployment') {
      environment{
    	CLIENT_ID = credentials('DEV_CLIENT_ID')
    	CLIENT_SECRET = credentials('DEV_CLIENT_SECRET')
    }
    	steps {
            bat 'mvn -U -V -e -B -DskipTests -Pdev deploy -DmuleDeploy -Danypoint.username=%ANYPOINT_CREDS_USR% -Danypoint.password=%ANYPOINT.CREDS_PSW% -Danypoint.platform.client_id=%CLIENT_ID% -Danypoint.platform.client_secret=%CLIENT_SECRET%'
      }
    }
    
  }
}