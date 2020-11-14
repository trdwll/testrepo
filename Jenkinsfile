pipeline {
  agent {
    node {
      label 'Windows'
      customWorkspace 'UE4PluginDev/testrepo'
    }

  }
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            bat 'C:\\build-scripts/UE4PluginDev/build.bat'
          }
        }

        stage('Build Release') {
          steps {
            bat '"${tool \'MSBuild\'}" testr-wfa/testr-wfa.csproj /p:Configuration=Release'
            tool(name: 'MSBuild sss', type: 'type')
          }
        }

        stage('Build Debug') {
          steps {
            bat '"${tool \'MSBuild\'}" testr-wfa/testr-wfa.csproj /p:Configuration=Debug'
          }
        }

      }
    }

  }
  options {
    disableConcurrentBuilds()
  }
}