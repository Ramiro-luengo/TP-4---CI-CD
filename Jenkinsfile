pipeline {
  agent {
    node {
      label 'Build'
    }

  }
  stages {
    stage('Build') {
      steps {
        git(url: 'https://github.com/Ramiro-luengo/TP-4---CI-CD.git', branch: 'main')
        withGradle() {
          sh './gradlew init'
        }

        withGradle() {
          sh './gradlew bootRun'
        }

      }
    }

  }
}