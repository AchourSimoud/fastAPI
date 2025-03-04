pipeline {
    agent any
   triggers { upstream(upstreamProjects: 'job1,job2', threshold: hudson.model.Result.SUCCESS) }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
    }
}