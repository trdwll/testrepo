
pipeline {
  agent {
    node {
      label 'Windows'
    }

  }
  
  stages {
    
    stage('Build Release') {
      steps {
        bat "python C:\\test.py %WORKSPACE%"
      }
    }

    stage('Build Release') {
      steps {
        bat "\"${tool 'MSBuild'}\" testr-wfa/testr-wfa.csproj /p:Configuration=Release"
      }
    }

    stage('Build Debug') {
      steps {
        bat "\"${tool 'MSBuild'}\" testr-wfa/testr-wfa.csproj /p:Configuration=Debug"
      }
    }

  }
}
