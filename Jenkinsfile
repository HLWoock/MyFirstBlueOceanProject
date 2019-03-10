pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'building'
        bat(script: 'gradlew jar --info', returnStatus: true, returnStdout: true)
      }
    }
    stage('Test') {
      steps {
        echo 'unit testing'
        bat(script: 'gradlew test --info', returnStatus: true, returnStdout: true)
      }
    }
    stage('Document') {
      steps {
        echo 'create javadoc'
        bat(script: 'gradlew javadock --info', returnStatus: true, returnStdout: true)
      }
    }
    stage('Static Analysis') {
      steps {
        echo 'making static analysis'
        bat(script: 'gradle check --info', returnStatus: true, returnStdout: true)
      }
    }
    stage('Deploy') {
      steps {
        echo 'deploying'
      }
    }
  }
}