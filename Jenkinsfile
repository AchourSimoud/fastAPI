pipeline {
    agent any
    triggers{
        triggers { upstream(upstreamProjects: 'fastAPI', threshold: hudson.model.Result.SUCCESS) }
    }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
    }
}