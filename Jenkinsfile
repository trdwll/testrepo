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
        bat 'C:\\build-scripts/UE4PluginDev/build.bat'
      }
    }

  }
}
