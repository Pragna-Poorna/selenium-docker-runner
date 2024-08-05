pipeline {
    agent {
            label 'NODE1'
          }
    stages {
        stage('Bring grid up') {
            steps {
               bat "docker-compose -f grid.yaml up -d"
            }
        }
        stage('Run the Tests') {
             steps {
                bat "docker-compose -f test-suite.yaml up "
             }
        }
        // Additional stages
    }
    post {
            always {
                bat "docker-compose -f test-suite.yaml down"
                bat "docker-compose -f grid.yaml down"
                archiveArtifacts artifacts: 'output/emailable-report.html', followSymlinks: false
            }
        }
}