pipeline {
  agent {
    label 'Node-1'
  }

  triggers {
    githubPush()
  }

  stages {
    stage ('Build') {
      steps {
        echo 'Running build automation'
        sh 'cd app && mvn package'
        archiveArtifacts artifacts: 'app/target/*.jar', allowEmptyArchive: true
      }
    }
  }
}
