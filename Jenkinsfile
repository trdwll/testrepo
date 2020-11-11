pipeline {
  agent {
    node {
      label 'Windows'
      customWorkspace 'UE4PluginDev/Plugins/testrepo'
    }

  }
  stages {
    stage('Prep') {
      steps {
        bat 'C:\\build-scripts/UE4PluginDev/prep.bat'
      }
    }

    stage('Generate') {
      steps {
        bat 'C:\\build-scripts/UE4PluginDev/generate.bat'
      }
    }

    stage('Build') {
      steps {
        bat 'C:\\build-scripts/UE4PluginDev/build.bat'
      }
    }

  }
}