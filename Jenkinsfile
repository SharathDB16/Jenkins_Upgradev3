pipeline {
      agent any
      stages {
            stage ('Build') {
                  steps {
                        sh 'mvn -f java-tomcat-sample clean package'
                  }
            }
            stage ('Archive artifacts') {
                  steps {
                        archiveArtifacts artifacts: '**/*.war'
                  }
            }
            stage ('Deploy to Staging') {
                  steps {
                        build job: 'Deploy_application'
                  }
            }
      }
}