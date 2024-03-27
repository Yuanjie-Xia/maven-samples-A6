pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        git(url: 'https://github.com/Yuanjie-Xia/maven-samples.git', branch: 'master')
      }
    }

    stage('run') {
      steps {
        sh '''/opt/homebrew/bin/mvn clean test'''
      }
    }

  }
  tools {
    maven 'roger_mvn'
    jdk 'Java8'
  }
}
