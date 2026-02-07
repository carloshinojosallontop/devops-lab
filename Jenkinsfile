pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        echo 'Repo clonado OK'
        sh 'ls -la'
      }
    }

    stage('Hello') {
      steps {
        echo 'Hola desde Jenkins'
        sh 'whoami'
        sh 'uname -a'
      }
    }
  }
}
