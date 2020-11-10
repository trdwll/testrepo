pipeline {
  agent {
    node {
      label 'Windows'
      customWorkspace 'UE4PluginDev/Plugins/testrepo'
    }
  }

  stages {
    stage('Build') {
      steps {
        sh 'printenv'
      }
    }
  }
}
