pipeline {
    agent any

    stages {
        stage('Verify Branch') {
            steps {
                echo "$GIT_BRANCH"
            }
        }
        stage('Docker Build') {
            steps {
                sh(script: 'docker images -a')
                sh(script: """
                    ls
                    cd azure-vote/
                    docker images -a
                    docker build -t jenkins-pipline .
                    cd ...
                """)
            }
        }
    }
}