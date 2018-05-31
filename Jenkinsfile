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
            mail to: 'cuongpm0503@gmail.com',
             subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
             body: "Something is wrong with ${env.BUILD_URL}"
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
