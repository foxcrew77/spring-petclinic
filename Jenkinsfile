#!groovy
pipeline {
    agent none
stages {
        stage('Checkout') {
            steps {
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[
                        url: 'https://github.com/foxcrew77/spring-petclinic.git',
                        credentialsId: 'b9d7ccbd-bbe8-41e5-aec2-a66f2d08086d' // Replace with your credential ID
                    ]]
                ])
            }
        }
   stages {     
    stage('Maven Install') {
      agent {         
       docker {          
         image 'maven:3.5.0'         
     }       
  }       
  steps {
       sh 'mvn clean install'
       }
     }
   }
 }
