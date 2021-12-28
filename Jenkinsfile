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
        script {
          echo("head ${pullRequest.head}")
          echo("headRef ${pullRequest.headRef}")
          echo("base ${pullRequest.base}")
          echo("mergeCommitSha ${pullRequest.mergeCommitSha}")
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
