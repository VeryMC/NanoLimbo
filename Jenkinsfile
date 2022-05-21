pipeline {
  agent {
    docker {
      args '-v /root/.m2:/root/.m2'
      image 'gradle:7.4.2-jdk11'
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
