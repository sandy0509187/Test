pipeline {
    agent any
    parameters {
        choice(name: 'Version' , choices: ['1.1.0', '1.2.0'])
    } 
    stages {
        stage("build") {
            steps {
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
            }
        }
        stage("test") {
            when {
                expression {
                    BRANCH_NAME == 'dev' || BRANCH_NAME == 'master'
                }
            }
            steps {
                echo 'test'
            }
        }
        stage ("deploy") {
            steps {
                echo 'deploying'
                echo "deploying version ${params.Version}"
            }
        }
    }
}
