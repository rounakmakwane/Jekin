stage('Build'){
  script{
    try {
      if(isUnix()){
          sh 'mvn clean package'
      }else{
       bat 'mvn clean package'
      }
    } catch(err) {
    throw err
    }
   }
}
