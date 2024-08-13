pipeline{

    agent any

    stages{

        stage('Star Grid'){
            steps{
                 sh "docker-compose -f grid.yaml up -d"
            }
        }
        stage('Run Test'){
            steps{
                sh "docker-compose -f test-suites.yaml up"
            }
        }
        
    }

    post{
        always{
            sh "docker-compose -f grid.yaml down"
            sh "docker-compose -f test-suites.yaml down"
        }
    }
}