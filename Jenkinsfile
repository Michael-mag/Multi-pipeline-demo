pipeline {
    agent any
    environment {
        PATH = "/usr/local/Cellar/maven/3.8.1/bin:$PATH"
    }
    tools {
        maven 'maven 3.8.1'
        jdk 'jdk8'
    }
    stages {
        stage ('SCM Checkout') {
            steps {
                git 'https://github.com/Michael-mag/Multi-pipeline-demo.git'
                sh 'pwd'
                sh 'ls'
            }
        }
        stage ('Initialize') {
            steps {
                /* groovylint-disable-next-line GStringExpressionWithinString */
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
            }
        }

        stage ('Build') {
            steps {
                sh 'mvn clean install'
                sh 'mvn test'
            }
            post {
                success {
                    cleanWs()
                }
            }
        }
    }
}