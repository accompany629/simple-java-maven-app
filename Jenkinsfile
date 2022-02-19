pipeline {
  agent {
    docker {
      args '-v /root/.m2:/root/.m2'
      image 'maven:3.5.4-alpine'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'mvn -B -DskipTests clean package'
      }
    }
    stage('Test') {
                steps {
                    sh 'mvn test'
                }
                post {
                    always {
                        junit 'target/surefire-reports/*.xml'
                    }
                }
            }stage('Test') {
                         steps {
                             sh 'mvn test'
                         }
                         post {
                             always {
                                 junit 'target/surefire-reports/*.xml'
                             }
                         }
                     }

  }
}