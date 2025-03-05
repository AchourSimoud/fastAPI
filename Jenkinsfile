pipeline{
    agent {
        docker {
            image "postman/newman"
            args "-u root" 
        }
    }
        

    triggers { upstream(upstreamProjects: '', threshold: 
    hudson.model.Result.SUCCESS) }

    stages{
        stage('verifier la version de newman'){
            steps{
                sh 'newman --version'
            }
        }

        stage('Install htmlextra'){
            steps{
                sh 'npm install newman-reporter-htmlextra'
            }
            
        }

        stage('Test API'){
            steps{
                sh 'newman run collections/Collection1.json --reporters htmlextra --reporter-htmlextra-export reports/api-test-report.html'
            }
        }
    }
    post{
        always {
            echo 'Archivage des rapports...'
            archiveArtifacts artifacts: 'reports/api-test-report.html', fingerprint: true
        }
    }
}