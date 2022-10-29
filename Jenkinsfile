pipeline {
  agent any
  tools {
    maven 'Maven' 
  }
  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean install'
      }
    }
    stage ('Deploy') {
      steps {
        script {
          deploy adapters: [tomcat8(credentialsId: 'd4eda513-6d81-45d6-bcfd-29f02d5924d5', path: '', url: 'http://ec2-52-91-233-121.compute-1.amazonaws.com:8080/')], contextPath: null, war: '**/*.war' 
        }
      }
    }
  }
}
