// Jenkinsfile (Declarative Pipeline)
pipeline {
    agent any 
    stages {
        stage('STEP-1 Static Code Analysis - SonarQube') { 
            steps {
                sh 'mvn clean verify sonar:sonar -DskipTests'
            }
        }
        stage('STEP-2 Clean') { 
            steps {
                sh 'mvn clean'
            }
        }
        stage('STEP-3 Validate') { 
            steps {
                sh 'mvn validate'
            }
        }
    }
}