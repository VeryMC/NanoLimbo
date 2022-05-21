pipeline {
  agent {
    docker {
      args '-v /root/.m2:/root/.m2'
      image 'gradle:6.9.2-jdk17'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'gradle shadowJar'
      }
    }

  }
  post {
    always {
      archiveArtifacts(artifacts: 'target/*.jar', fingerprint: true)
    }

  }
}
