pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        git(url: 'https://github.com/abhijat/jenkins2-course-spring-petclinic.git', branch: 'master')
      }
    }
    stage('compile, test and verify') {
      steps {
        sh 'mvn clean verify package'
      }
    }
    stage('notify') {
      steps {
        mail(subject: 'job complete - ${env.JOB_NAME}', body: 'The job is done!', from: 'malviya.abhijat@gmail.com', to: 'malviya.abhijat@gmail.com')
      }
    }
  }
}