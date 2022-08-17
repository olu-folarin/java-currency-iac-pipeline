// old way jenkins scripts were written and is known as a Scripted Pipeline. Here, node refers to a machine

// node {
// 		echo "Build"
// 		echo "Test"
// 		echo "Integration Test"
// }

// declarative pipeline is better
pipeline {
    agent any
    // agent { docker { image 'maven:3.8.6' } }

    // getting the maven and docker environments
    // environment {
    //     dockerHome = tool 'myDocker'
    //     mavenHome = tool 'myMaven'
    //     // add them to path
    //     PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
    // }

    stages {
        stage('Checkout') {
            steps {
                sh 'mvn --version'
                sh 'docker version'
                echo "Build"
                echo "$PAth - $PATH"
                echo "$BUILD_ID - $env.BUILD_ID"
                echo "$JOB_NAME - $env.JOB_NAME"
                echo "$BUILD_TAG - $env.BUILD_TAG"
                echo "$BUILD_URL - $env.BUILD_URL"
                echo "$BUILD_NUMBER - $env.BUILD_NUMBER"
            }
        }
        stage('Compile') {
            steps {
                sh "mvn clean compile"
            }
        }
        // tests
        stage('Test') {
            steps {
                sh "mvn test"
            }
        }
        stage('Integration Test') {
            steps {
                sh "mvn failsafe:integration-test failsafe:verify"
            }
        }
    } 
    post {
        always {
            echo 'I am running.'
        }
        success {
            echo 'successful!'
        }
        failure {
            echo 'failed!'
        }
    }
}
