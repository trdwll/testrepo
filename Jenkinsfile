pipeline {
  agent {
    node {
      label 'Windows'
      customWorkspace 'UE4PluginDev/testrepo'
    }

  }
  stages {

    stage('Build Release') {
      steps {
        bat '\"${MSBUILD}\" testr-wfa/testr-wfa.csproj /p:Configuration=Release;Platform=x64'
      }
    }

    stage('Build Debug') {
      steps {
        bat '\"${MSBUILD}\" testr-wfa/testr-wfa.csproj /p:Configuration=Debug;Platform=x64'
      }
    }

  }
  environment {
    MSBUILD = "C:\\Program Files (x86)\\Microsoft Visual Studio\\2019\\Community\\MSBuild\\Current\\Bin\\msbuild.exe"
  }
  options {
    disableConcurrentBuilds()
  }
}
