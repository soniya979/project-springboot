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
        stage('STEP-4 test') { 
            steps {
                sh 'mvn test'
            }
        }
        stage('STEP-5 install') { 
            steps {
                sh 'mvn install'
            }
        }
        stage('STEP-6 package') { 
            steps {
                sh 'mvn package'
            }
        }
        stage('STEP-7 deploy') { 
            steps {
                sh 'mvn deploy'
            }
        }

    }
}