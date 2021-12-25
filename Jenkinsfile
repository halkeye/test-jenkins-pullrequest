pipeline {
  agent any
  stages {
    stage('test') {
      steps {
        script {
          def comment = pullRequest.comments.toList.find { it.body.include("<!-- DEPLOY PREVIEW -->") }
          if (comment != null) {
            pullRequest.editComment(comment.id, "<!-- DEPLOY PREVIEW --> EDITED COMMENT")
          } else {
            pullRequest.postComment("<!-- DEPLOY PREVIEW --> NEW COMMENT")
          }
        }
      }
    }
  }
}
