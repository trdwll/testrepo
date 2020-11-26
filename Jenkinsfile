pipeline {
  agent {
    node {
      label 'Windows'
      customWorkspace 'UE4PluginDev/testrepo'
    }

  }
  stages {
    stage('Build') {
      steps {
        bat 'C:\\build-scripts/UE4PluginDev/build.bat'
      }
    }

    stage('Build Release') {
      steps {
        bat '\"${MSBUILD}\" testr-wfa/testr-wfa.csproj /p:Configuration=Release'
      }
    }

    stage('Build Debug') {
      steps {
        bat '\"${MSBUILD}\" testr-wfa/testr-wfa.csproj /p:Configuration=Debug'
      }
    }

  }
  environment {
    MSBUILD = 'hudson.plugins.msbuild.MsBuildInstallation'
  }
  options {
    disableConcurrentBuilds()
  }
}
