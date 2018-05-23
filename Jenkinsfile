node {
    stage('build') {
        checkout scm
        withEnv(["PATH+MAVEN=${tool 'M3'}/bin"]) {
            sh 'pwd;ls'
            sh 'cd my-app;mvn clean verify'
        }
        archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
        junit '**/target/**/*.xml'
    }
    stage('integration test') {
      echo 'integration test'
    }
    stage('deploy') {

          if(currentBuild.result == null || currentBuild.result == 'SUCESUCCESSS') {
             echo "deploying ${currentBuild.number}"
          }
    }

}
