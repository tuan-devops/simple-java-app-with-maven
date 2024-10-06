pipeline {
  agent {
    label {
      label 'Node-1' // Run the pipeline on the Jenkins agent labeled 'Node-1'
      retries 2
    }
  }

  tools {
    maven 'M3'
  }

  triggers {
    githubPush() // Trigger the pipeline on push events
  }

  stages {
    stage ('Build') {
      when {
        branch 'main'
      }
      steps {
        echo 'Running build automation'
        sh '''
          cd app
          mvn package
        '''
        archiveArtifacts artifacts: 'app/target/*.jar', allowEmptyArchive: true
      }
    }
  }
}
