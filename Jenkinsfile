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
        stage('Build') {
            steps {
              bat 'mvn -B -DskipTests clean package'
            }
        }

        stage('Build and Send Results to Sonar') {
            steps {
                withSonarQubeEnv(installationName: 'sonarqube')
                { bat 'mvn clean package sonar:sonar -Dsonar.login=admin -Dsonar.password=Test'}
            }
        }

    }
}
