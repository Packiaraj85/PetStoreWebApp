pipeline {
  agent any
  stages {

    stage('clone') {
      steps {
        script {
          git credentialsId: 'git', url: 'https://github.com/Packiaraj85/javafirst.git'
          sh 'ls -lart'
        }
      }
    }

    stage('Parallel stages') {
      parallel {

        stage('Sequential nested stages') {
          stages {
            stage('Build') {
              steps {
                script {
                  sh 'mvn clean package'
                }
              }
            }
            stage('Test') {
              steps {
                script {
                  sh 'mvn test'
                }
              }
            }
          }
        }

        stage('Deploy') {
          steps {
            script {
              sh 'mvn instal'
            }
          }
        }

      }
    }

  }
}
