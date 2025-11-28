pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo "Building Java Application"
                sh 'mkdir -p build'
                sh 'javac Hello.java -d build'
            }
        }

        stage('Test') {
            steps {
                echo "Running Tests"
                sh 'mkdir -p test'
                sh 'javac HelloTest.java -d test'
                sh 'java -cp test HelloTest'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying Application"
                sh 'java -cp build Hello'
                echo "Deployment Completed"
            }
        }
    }
}
