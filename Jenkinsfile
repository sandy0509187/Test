pipeline {
    agent 'cloud'
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
            steps {
                echo 'test'
            }
        }
        stage ("deploy") {
            input {
              message "Deploy to stage? or abort"
              ok "Deploy"
            }
            steps {
                echo 'deploying'
                echo "deploying version ${params.Version}"
            }
        }
    }
}
