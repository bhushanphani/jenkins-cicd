pipeline {
  agent any
  stages {
  stage('SCM Checkout'){
      steps{
        git url: 'https://github.com/bhushanphani/jenkins-cicd.git'
      }
  }
    stage('Deploy CloudHub') { 
      environment {
        ANYPOINT_CREDENTIALS = credentials('anypoint.credentials')
      }
      steps {
        bat "mvn clean package deploy -DmuleDeploy -Danypoint.username=${ANYPOINT_CREDENTIALS_USR} -Danypoint.password=${ANYPOINT_CREDENTIALS_PSW} -Dmule.env=test"
      }
    }
  }
}
