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
        bat '"${env.MSBuild}" testr-wfa/testr-wfa.csproj /p:Configuration=Release'
      }
    }

    stage('Build Debug') {
      steps {
        bat '"${env.MSBuild}" testr-wfa/testr-wfa.csproj /p:Configuration=Debug'
      }
    }

  }
  environment {
    MSBuild = 'C:\\Program Files (x86)\\Microsoft Visual Studio\\2019\\Community\\MSBuild\\Current\\Bin\\MSBuild.exe'
  }
  options {
    disableConcurrentBuilds()
  }
}