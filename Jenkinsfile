pipeline {
  agent any

  tools {
    sonarQubeScanner 'SonarScanner'
  }

  stages {

    stage('Checkout') {
      steps {
        checkout scm
      }
    }

    stage('SonarQube Analysis') {
      steps {
        withSonarQubeEnv('SONAR') {
          sh '''
            sonar-scanner \
              -Dsonar.projectKey=devops-lab \
              -Dsonar.projectName=devops-lab \
              -Dsonar.sources=.
          '''
        }
      }
    }

    stage('Quality Gate') {
      steps {
        timeout(time: 5, unit: 'MINUTES') {
          waitForQualityGate abortPipeline: true
        }
      }
    }
  }
}
