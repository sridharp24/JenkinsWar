pipeline {
  agent any

  tools {
    maven 'maven-3.6.3' 
  }
  stages {

    stage ('clone code') {
      steps {
        git 'https://github.com/sridharp24/JenkinsWar.git'
      }
    }

    stage ('build code') {
      steps {
        sh 'mvn clean package'
      }
    }

   stage ('deploy war') {
      steps {        
        deploy adapters: [tomcat8(credentialsId: 'TomcatCred', path: '', url: 'http://localhost:9090')], contextPath: '/pline', war: '**/*.war'
        }
       }

      }
}
