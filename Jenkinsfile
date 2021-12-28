pipeline {
  agent any
  stages {
    stage('test') {
      steps {
        script {
          sh('printenv')
          def comment = pullRequest.comments.toList().find { it.body.contains("<!-- DEPLOY PREVIEW -->") }
          if (comment != null) {
            pullRequest.editComment(comment.id, "<!-- DEPLOY PREVIEW --> EDITED COMMENT")
          } else {
            pullRequest.comment("<!-- DEPLOY PREVIEW --> NEW COMMENT")
          }
        }
      }
    }
  }
}
