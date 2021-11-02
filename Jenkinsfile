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

    stage('Analyze') {
      steps {
        withGradle() {
          sh 'chmod +x gradle'
          sh './gradlew sonarqube'
        }

      }
    }

    stage('Jacoco') {
      steps {
        withGradle() {
          sh './gradlew jacocoTestReport'
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