pipeline {
    agent any

    stages {
	
        stage('CLONE GITHUB CODE') {
            steps {
                echo 'In this stage code will be clone'
				git branch: 'main', url: 'https://github.com/devopstraininghub/mindcircuit15d.git'
				
				}
        }
		
        stage('BUILDING THE CODE') {
            steps {
                echo 'In this stage code will be build and mvn artifact will be generated'
				sh 'mvn clean install '
				
            }
        }		
		
        stage('DEPLOY') {
            steps {
                echo 'In this stage .war artiface will be deployed on to tomcat '
		deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://44.222.151.217:8080/')], contextPath: 'WEB', war: '**/*.war'
				
            }
        }		
		
		
    }
}
