pipeline {
     agent {
        docker { image 'maven:3.3.3' }
    }
    stages {
        /* "Build" and "Test" stages omitted */

        stage('Deploy - Staging') {
            steps {
                sh 'ls'
            }
        }

        stage('Sanity check') {
            steps {
                input "Doessss the staging environment look ok?"
            }
        }

        stage('Deploy - Production') {
            steps {
                sh 'ls'
            }
        }
    }
}
