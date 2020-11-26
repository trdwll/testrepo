
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
        bat "\"${tool 'MSBuild'}\" testr-wfa/testr-wfa.csproj /p:Configuration=Release;Platform=x64"
      }
    }

    stage('Build Debug') {
      steps {
        bat 'msbuild.exe testr-wfa/testr-wfa.csproj /p:Configuration=Debug;Platform=x64'
      }
    }

  }
}
