pipeline {
  agent {
    node {
      label 'Windows'
      customWorkspace 'UE4PluginDev/Plugins'
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