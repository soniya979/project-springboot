pipeline {
    agent any 
    stages {
        stage('Stage-0 : Static Code Quality'){
            steps  {
                withMaven(maven : 'maven'){
                    sh 'mvn clean verify sonar:sonar -DskipTests'
                }
            }
        } 
        stage('Stage-1 : Clean'){
            steps  {
                withMaven(maven : 'maven'){
                    sh 'mvn clean'
                }
            }
        }
        stage('Stage-2 : Validate') { 
            steps {
                withMaven(maven : 'maven'){
                    sh 'mvn validate'
                } 
            }
        }
        stage('Stage-3 : Compile') { 
            steps {
                withMaven(maven : 'maven'){
                    sh 'mvn compile'
                } 
            }
        }
        stage('Stage-4 : Test') { 
            steps {
                withMaven(maven : 'maven'){
                    sh 'mvn test -DskipTests'
                } 
            }
        }
        stage('Stage-5 : Install') { 
            steps {
                withMaven(maven : 'maven'){
                    sh 'mvn install -DskipTests'
                } 
            }
        }
        stage('Stage-6 : Verify') { 
            steps {
                withMaven(maven : 'maven'){
                    sh 'mvn verify -DskipTests'
                } 
            }
        }
        stage('Stage-7 : Package') { 
            steps {
                withMaven(maven : 'maven'){
                    sh 'mvn package -DskipTests'
                } 
            }
        }
        stage('Stage-8 : Deploy an Artifact to Artifactory Manager i.e. Nexus/Jfrog') { 
            steps {
                withMaven(maven : 'maven'){
                    sh 'mvn deploy -DskipTests'
                } 
            }
        }
        
        stage('Stage-9 : Deployment - Deploy a Artifact staragile-3.1.0.war file to Tomcat Server '){
            steps{
                sh 'curl -u admin:redhat@123 -T target/**.war "http://18.116.20.170:8080/manager/text/deploy?path=/staragile&update=true"' 
            }
        }
        stage('Stage-10 : SmokeTest'){
            steps{
                sh 'curl --retry-delay 10 --retry 5 "http://18.116.20.170:8080/staragile"' 
            }
        }
    }
}
