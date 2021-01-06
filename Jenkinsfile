pipeline {
  agent any
  stages {
    stage('Code') {
      steps {
        sh 'echo "start the pipeline"'
        git(url: 'https://github.com/kunjjain11/simple_maven.git', branch: 'master', changelog: true, poll: true)
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
        sh 'java -jar target/'
      }
    }

    stage('Pipeline_End') {
      steps {
        sh 'echo "All success"'
      }
    }

  }
}