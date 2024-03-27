pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        git(url: 'https://github.com/Yuanjie-Xia/maven-samples-A6.git', branch: 'master')
      }
    }

    stage('run1') {
      steps {
        sh '''git bisect start&&

git bisect good 98ac319c0cff47b4d39a1a7b61b4e195cfa231e5&&

git bisect bad 198644632661c67b6c32f59e9047c11a70685e15'''
      }
    }

    stage('run2') {
      steps {
        sh 'git bisect bad 8bad1c6db9cf6930abd8e52ff5dfdd046194ae9b'
      }
    }

    stage('mvn') {
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