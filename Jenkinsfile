pipeline {
  agent any
  stages {
    stage('test') {
      steps {
        script {
          pullRequest.postComment("HI THERE")
          pullRequest.comments.toList().each { echo(it.user.toString()) }
        }
      }
    }
  }
}
