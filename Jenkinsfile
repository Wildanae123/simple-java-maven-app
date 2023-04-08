node {
	docker.image('maven:3.9.0-eclipse-temurin-11').inside('-v /root/.m2:/root/.m2')
    {		
        stage('Build') {
            sh 'mvn -B -DskipTest clean package'
        }
        stage('Test') {            
            sh 'mvn test'
            junit 'target/surefire-reports/*.xml'
        }        
	}
}
