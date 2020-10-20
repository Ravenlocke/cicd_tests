pipeline {
    agent none 
    stages {
        stage('Build') { 
            agent {
                docker {
                    image 'python:3-alpine' 
                }
            }
            steps {
                withEnv(["HOME=${env.WORKSPACE}"]) {
                    sh 'ls'
                    sh 'python -m pip install -U tox'
                    sh 'python -m tox' 
                }
            }
        }
    }
}
