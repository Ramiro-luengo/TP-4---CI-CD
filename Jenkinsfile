pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        git(url: 'https://github.com/Ramiro-luengo/TP-4---CI-CD.git', branch: 'main')
        withGradle() {
          sh './gradlew init'
          sh './gradlew bootRun'
        }

      }
    }

  }
}