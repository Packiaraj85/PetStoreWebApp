pipeline {
  agent any
  stages {

    stage('clone') {
      steps {
        script {
          git credentialsId: 'git', url: 'https://github.com/Packiaraj85/javafirst.git'
          sh 'pwd'
          sh 'ls -lart'
        }
      }
    }

    stage('Parallel stages') {
      parallel {

        stage('Sequential nested stages') {
          stages {
            stage('Stage 2') {
              steps {
                script {
                  sh 'mvn clean package'
                  sh 'sleep 20'
                }
              }
            }
            stage('Stage 3') {
              steps {
                script {
                  echo 'Stage 3'
                  sh 'sleep 20'
                }
              }
            }
          }
        }

        stage('Stage 4') {
          steps {
            script {
              echo 'Stage 4'
              sh 'sleep 20'
            }
          }
        }

      }
    }

  }
}
