pipeline {
  agent {
    docker {
      image 'maven:3-openjdk-11'
    }

  }
  stages {
    stage('build') {
      steps {
        sh 'mvn compile'
      }
    }

    stage('test') {
      steps {
        sh 'mvn clean test'
      }
    }

    stage('package') {
      steps {
        sh 'mvn package -DskipTests'
        archiveArtifacts '**/target/*.war'
      }
    }

  }
  tools {
    maven 'Maven363'
  }
}