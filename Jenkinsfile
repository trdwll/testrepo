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
            tool(name: 'MSBuild', type: 'hudson.plugins.msbuild.MsBuildInstallation')
            bat '"${tool \'MSBuild\'}" testr-wfa/testr-wfa.csproj /p:Configuration=Release'
          }
        }

        stage('Build Debug') {
          steps {
            tool(name: 'MSBuild', type: 'hudson.plugins.msbuild.MsBuildInstallation')
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