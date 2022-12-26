pipeline{
    agent{
        node{
            label 'master'
        }
    }

    options{
        timestamps ()
    }

    stages{
        stage ("checkout, Test & Publish") {
            steps{
                checkout scm
                script {
                    sh (/mvn clean test/)
                }

                step ([$class : 'Publisher', reportFilePattern : '**/testng-results.xml'])
            }
        }
    }
}
