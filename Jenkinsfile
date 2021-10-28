pipeline {
    agent { dockerfile true }
    stages {
	stage('Prepare') {
      		git 'https://github.com/cicdTrainer/spring-boot-demo.git'
      		
        }
	stage('package') {
	 mvn package && java -jar target/my-image:${env.BUILD_ID}.jar
	}
        stage('build image') {
            steps {
               def customImage = docker.build("my-image:${env.BUILD_ID}")
            }
        }
    }
}