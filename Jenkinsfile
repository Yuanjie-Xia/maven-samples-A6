pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        git(url: 'https://github.com/Yuanjie-Xia/maven-samples.git', branch: '198644632661c67b6c32f59e9047c11a70685e15')
      }
    }

    stage('run') {
      steps {
        sh '/opt/homebrew/bin/mvn clean test'
      }
    }

  }
  tools {
    maven 'roger_mvn'
    jdk 'Java8'
  }
}