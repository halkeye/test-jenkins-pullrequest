pipeline {
  agent any
  stages {
    stage('test') {
      steps {
        script {
          pullRequest.comments.toList().each { echo(it.user.toString()) }
        }
      }
    }
  }
}
