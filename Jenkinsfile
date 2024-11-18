pipeline {
    agent any

    environment {
        GIT_CREDENTIALS = credentials('github-credentials')  // Reference to Jenkins stored credentials
    }

    stages {
        stage('Checkout') {
            steps {
                script {
                    // Clone the GitHub repository using Jenkins credentials
                    checkout([$class: 'GitSCM', branches: [[name: '*/main']], 
                        doGenerateSubmoduleConfigurations: false, 
                        extensions: [], 
                        userRemoteConfigs: [[url: 'https://github.com/unipod-inc/Unipod-booking-System.git', credentialsId: 'github-credentials']]])
                }
            }
        }

        stage('Build') {
            steps {
                // Execute the Maven build
                script {
                    sh 'mvn clean package'
                }
            }
        }

        stage('Test') {
            steps {
                // Publish test results
                junit '**/target/surefire-reports/*.xml'
            }
        }

        stage('Archive') {
            steps {
                // Archive JAR files
                archiveArtifacts '**/target/*.jar'
            }
        }

        stage('Notify') {
            steps {
                // Send email notification on failure
                mail to: 'qthmichaels@gmail.com',
                     subject: "Build ${currentBuild.fullDisplayName} failed",
                     body: "The build has failed. Please check Jenkins for more details."
            }
        }
    }

    post {
        always {
            echo 'Build completed'
        }
    }
}
