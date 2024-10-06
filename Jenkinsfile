pipeline {
  agent {
    label 'Node-1' // Run the pipeline on the Jenkins agent labeled 'Node-1'
  }

  tools {
    maven 'M3'
  }

  triggers {
    githubPush() // Trigger the pipeline on push events
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
