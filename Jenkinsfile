pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        git(url: 'https://github.com/Yuanjie-Xia/maven-samples-A6.git', branch: 'master')
      }
    }

    stage('run') {
      parallel {
        stage('run1') {
          steps {
            sh 'git checkout 8bad1c6db9cf6930abd8e52ff5dfdd046194ae9b'
          }
        }

        stage('run2') {
          steps {
            sh 'git checkout 26438de182f7a00147b5e53e9408a3c3745ca509'
          }
        }

        stage('run3') {
          steps {
            sh 'git checkout 34d31973a0cc1f3d77cd5038fc9c01eeba7ec183'
          }
        }

      }
    }

    stage('mvn clean test') {
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