pipeline {

  agent {
    label 'Linux'
  }

  stages {

    stage ('Script') {

      steps {
        sh 'chmod +x rondoudou.sh'
	  sh './rondoudou.sh'
      }

    }
  
  }

}
