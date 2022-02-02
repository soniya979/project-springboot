// Jenkinsfile (Declarative Pipeline)
pipeline {
    agent any 
    stages {
       // stage('STEP-1 Static Code Analysis - SonarQube') { 
       //     steps {
       //         sh 'mvn clean verify sonar:sonar -DskipTests'
       //     }
       // }
        stage('Clean') { 
            steps {
                sh 'mvn clean'
            }
        }
        stage('Validate') { 
            steps {
                sh 'mvn validate'
            }
        }
        stage('test') { 
            steps {
                sh 'mvn test -DskipTests'
            }
        }
        stage('install') { 
            steps {
                sh 'mvn install -DskipTests'
            }
        }
        stage('package') { 
            steps {
                sh 'mvn package -DskipTests'
            }
        }
        stage('Deployment - Deploy a Artifact eficens-1.0.0.war file to Tomcat Server') { 
            steps {
                sh 'curl -u admin:redhat@123 -T target/**.war "http://54.215.60.73:8080/manager/text/deploy?path=/eficens&update=true"'
            }
        }
        stage('SmokeTest') { 
            steps {
                sh 'curl --retry-delay 10 --retry 5 "http://54.215.60.73:8080/eficens"'
            }
        }
    }
}
