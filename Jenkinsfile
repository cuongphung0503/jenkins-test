pipeline {
     agent {
        docker { image 'maven:3.3.3' }
    }
    stages {
        stage('No-op') {
            steps {
                sh 'ls'
            }
        }
    }
    post {
        success {
            slackSend channel: '#slacktest',
                  color: 'good',
                  message: "The pipeline ${currentBuild.fullDisplayName} completed successfully."
        }
        unstable {
            echo 'I am unstable :/'
        }
        failure {
            echo 'I failed :('
        }
        changed {
            echo 'Things were different before...'
        }
    }
}
