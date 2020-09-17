pipeline {
  agent any
  stages {
  stage('Stage 1') {
      steps {
        script {
          echo 'Stage 1'
        }
      }
    }
  stage('Stage 2') {
      steps {
             script {
              echo 'START'
              echo '${env.ec3}'
              sshPublisher(
               continueOnError: false, failOnError: true,
               publishers: [
                sshPublisherDesc(
                 configName: "${env.ec3}",
                 verbose: true,
                 transfers: [
                  sshTransfer(
                   sourceFiles: "*/",
                   removePrefix: "",
                   remoteDirectory: "/jenkin",
                   execCommand: "ls"
                  )
                 ])
               ])
              }
      }
    }
  }
}
