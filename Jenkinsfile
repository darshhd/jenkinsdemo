pipeline {
  agent any
  stages {
    stage('code collection') {
      steps {
        git(url: 'https://github.com/darshhd/jenkinsdemo.git', changelog: true, poll: true)
      }
    }

    stage('compile') {
      steps {
        sh 'mvn clean;mvn compile'
      }
    }

    stage('test') {
      steps {
        sh 'mvn test'
      }
    }

    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }

    stage('report publish') {
      steps {
        junit 'target/surefire-reports/*.xml'
      }
    }

  }
}