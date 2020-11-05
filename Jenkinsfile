pipeline {
    agent any

    stages {
        stage('Compile') {
            steps {
                echo 'Helloo world'
                sh 'go build'
            }
        }
        stage('Test') {
            steps {
                sh 'go test -v'
            }
        }
        stage('Release') {
            environment {
                GITHUB_TOKEN = credentials('hello')
            }
            steps {
                sh 'rm gohello'
                sh 'rm -r dist'
                sh 'curl -sL https://git.io/goreleaser | sh'
            }
        }
    }
}
