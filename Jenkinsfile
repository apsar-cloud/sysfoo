pipeline {
    agent any

    tools {
      Maven 'Maven 3.6.3' 
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'mvn comiple'
            }
            }

        stage('Test') {
            steps {
                echo 'Testing'
                sh 'mvn test'
				
            }
        }
        stage('Pachage') {
            steps {
                echo 'Packaging....'
                sh 'mvn package -DskipTests'
		archiveArtifacts artifacts: '**/target/*.war', fingerprint: true
            }
        }
    }
}
