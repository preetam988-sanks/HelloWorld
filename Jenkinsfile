pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from the repository
                git url: 'https://github.com/preetam988-sanks/HelloWorld.git', branch: 'master' // Update branch if needed
            }
        }
        stage('Compile') {
            steps {
                // Compile the HelloWorld.java file
                sh 'javac HelloWorld.java'
            }
        }
        stage('Run') {
            steps {
                // Run the compiled Java program
                sh 'java HelloWorld'
            }
        }
    }

    post {
        success {
            echo 'Build and run completed successfully!'
        }
        failure {
            echo 'Build or run failed.'
        }
    }
}
