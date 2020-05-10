pipeline {
    agent {
        docker {
            image 'gradle:jdk11'
        }
    }

    stages {
        stage('Build') {
            steps {
                echo "Gradle assembling project.."
                sh './gradlew assemble'
            }
        }
        stage('Tests') {
            steps {
                echo "Gradle executing tests.."
                sh './gradlew check'
            }
        }
        stage('Mutation Tests') {
            steps {
                echo "Gradle executing mutation tests.."
                sh './gradle pitest'
            }
        }
    }
}
