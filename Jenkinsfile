pipeline {
  agent any
  environment { 
    docker_username = "frederikam"
  }
  stages {
    stage('Parallel Execution') {
      parallel {
        stage('Say Hello') {
          steps {
            sh 'echo "hello world"'
          }
        }

        stage('Build App') {
          agent {
            docker {
              image 'gradle:jdk11'
            }

          }
          steps {
            sh 'sh ci/build-app.sh'
          }
        }

      }
    }
  }
}
