pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build'
                sh 'mvn clean install -e'
                sh 'mvn package'
            }
        }
        
         stage("sonar") {
            agent any
            steps {
              withSonarQubeEnv(installationName:'sonar', credentialsId:'sonar') {
                sh 'mvn sonar:sonar -Dsonar.projectKey=chalasani1 -Dsonar.organization=chalasani1''
              }
            }
          }

    
    }
}
