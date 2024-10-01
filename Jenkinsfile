pipeline {
    agent any

    tools {
        jdk 'JAVA_HOME'
        maven 'MAVEN_HOME'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/preetam988-sanks/HelloWorld.git'
            }
        }

        stage('Build') {
            steps {
                dir('HelloWorld') { // Adjust this if needed
                    sh 'mvn clean install'
                }
            }
        }

        stage('Test') {
            steps {
                dir('HelloWorld') { // Adjust this if needed
                    sh 'mvn test'
                }
            }
        }

        stage('Package') {
            steps {
                dir('HelloWorld') { // Adjust this if needed
                    sh 'mvn package'
                }
            }
        }

        stage('Run') {
            steps {
                dir('HelloWorld') { // Adjust this if needed
                    sh 'java -jar target/your-app-name-1.0-SNAPSHOT.jar'
                }
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: 'HelloWorld/target/*.jar', allowEmptyArchive: true
        }

        success {
            echo 'Build succeeded!'
        }

        failure {
            echo 'Build failed.'
        }
    }
}
