pipeline {
  agent any
  stages {
    stage('error') {
      steps {
        sh 'echo \'Welcome to Blue Ocean\''
        git(url: 'https://github.com/anveshiv/simple_maven.git', branch: 'master', changelog: true, poll: true)
      }
    }

    stage('Compile') {
      steps {
        sh 'mvn compile'
      }
    }

    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }

    stage('Deploy') {
      steps {
        sh 'java -jar target/gs-maven-0.1.0.jar'
      }
    }

    stage('End') {
      steps {
        sh 'echo \'End of pipeline\''
      }
    }

  }
}