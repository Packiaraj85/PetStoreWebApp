pipeline {
  agent any
  stages {

    stage('checkout clone') {
      steps {
        script {
          git credentialsId: 'git', url: 'https://github.com/Packiaraj85/javafirst.git'
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
            stage('deploy') {
              steps {
                script {
                  sh 'mvn install'
                }
              }
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

  }
}
