pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                    echo 'deploy'
            }
        }
    
    stage('SSH transfer') {
     script {
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
