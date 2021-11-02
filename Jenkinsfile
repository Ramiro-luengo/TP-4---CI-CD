pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        git(url: 'https://github.com/Ramiro-luengo/TP-4---CI-CD.git', branch: 'main')
        withGradle() {
          sh 'chmod +x gradlew'
          sh './gradlew init'
          sh './gradlew bootRun'
        }

      }
    }

    stage('Test') {
      steps {
        withGradle() {
          sh 'chmod +x gradle'
          sh './gradlew test'
        }

      }
    }

    node {
  stage('Analyze') {
    git 'https://github.com/foo/bar.git'
  }
  stage('SonarQube analysis') {
    withSonarQubeEnv() { // Will pick the global server connection you have configured
      sh './gradlew sonarqube'
    }
  }
  }
    stage('Validate') {
      steps {
        sh 'echo Validate!'
      }
    }

    stage('Deploy') {
      steps {
        sh 'echo Deployed!'
      }
    }

  }
}