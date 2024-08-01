pipeline {
    agent any
    stages {
        stage('Run Tests') {
            steps {
               bat "docker-compose up"
            }
        }
        stage('Bringing containers down') {
            steps {
               bat "docker-compose down"
            }
        }
        // Additional stages
    }
}