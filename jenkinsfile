pipeline{
    agent any
    stages {
        stage('Test'){
            steps {
                bat 'mvn clean compile test'
                echo "Testing is done"
                }
        }
        stage('Build') {
            steps {
              bat 'mvn package'
            }
        }
        
    }
}
