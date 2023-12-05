pipeline{
    agent any
    tools {
        maven "localMaven"
    }
    stages {
        stage('Test'){
            steps {
                bat 'mvn clean compile test'
                echo "Testing is done"
                }
        }
        stage('Build and send results to Sonarqube') {
            steps {
              withSonarQubeEnv(installationName: 'sonarqube'){   
                  bat 'mvn -B -DskipTests clean package'}
            }
        }
    }
}
