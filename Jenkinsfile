pipeline {

  agent {
    label 'Linux'
  }

  stages {

    stage ('Script') {

      steps {
        sh 'chmod +x test_mb_jenkins.sh'
	  sh './test_mb_jenkins.sh'

      }

    }
	stage ('Packaging') {

      steps {
        sh 'cd /home/jenkins/test_maven && mvn package -DskipTests'
      }
    }
	stage ('Testing') {

      steps {
        sh 'cd /home/jenkins/test_maven'
	sh 'mvn test'
      }
    }
	stage ('Delivery') {

      steps {
        sh 'cd /home/jenkins/test_maven/target'
	sh 'curl -u admin:Azerty@01 --upload-file test_maven-1.0-SNAPSHOT.jar "http://10.10.20.31:8081/repository/depot_test/test.jar"'
      }
    }  
  
  }

}
