pipeline {
  agent any
  stages {
    stage('foo') {
      steps {
        echo "bar"
      }
    }
    stage('test') {
      steps {
        echo(pullRequest.comments)
      }
    }
  }
}
