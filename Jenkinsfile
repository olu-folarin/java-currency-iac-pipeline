// old way jenkins scripts were written and is known as a Scripted Pipeline. Here, node refers to a machine

node {
		echo "Build"
		echo "Test"
		echo "Integration Test"
}

// declarative pipeline is better
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Build"
            }
        }
    }
    stages {
        stage('Test') {
            steps {
		        echo "Test"
            }
        }
    }
    stages {
        stage('Integration Test') {
            steps {
		        echo "Integration Test"
            }
        }
    }
}
