pipeline {
  agent {
    node {
      label 'Windows'
    }

  }
  stages {
    stage('Build Plugin') {
      steps {
        bat 'py -u C:\\jenkins.py buildbreaker Build "%WORKSPACE%"'
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

    stage('Publish Release') {
      when {
        branch 'main'
      }
      steps {
        bat 'py C:\\jenkins.py testr-wfa Publish "%WORKSPACE%"'
      }
    }

    stage('s') {
      steps {
        googleStorageUpload(credentialsId: 'test', bucket: 'bucket', pattern: 'pattern', pathPrefix: 'prefix')
      }
    }

  }
}