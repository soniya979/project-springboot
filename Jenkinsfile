pipeline {
    agent any
    tools {
        maven '3.6.0'
        jdk 'jdk8'

    }
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                echo "PATH = ${PATH}"
                echo "M2_HOME = ${M2_HOME}"
                '''
            }
        }
        stage ('Build') {
            steps {
                echo 'This is a  minimal pipeline'
            }
        }

    }

}