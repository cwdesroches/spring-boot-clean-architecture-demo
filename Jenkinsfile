pipeline {
    agent {
        docker {
            image 'gradle:jre11'
        }
    }

    stages {
        stage('Build') {
            steps {
                echo "Gradle assembling project.."
                sh 'gradle assemble'
            }
        }
        stage('Tests') {
            steps {
                echo "Gradle executing tests.."
                sh 'gradle check'
            }
        }
        stage('Mutation Tests') {
            steps {
                echo "Gradle executing mutation tests.."
                sh 'gradle pitest'
            }
        }
    }
}
