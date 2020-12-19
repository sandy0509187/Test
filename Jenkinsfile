## pipeline must be top level ####
##agent where to execute ###

pipeline {
    agent any
    parameters {
        choice(name: 'Version' , choices: ['1.1.0', '1.2.0'])
    } 
    stages {
        stage("build") {
            steps {
                echo 'build'
            }
        }
        stage("test") {
            when {
                expression {
                    BRANCH_NAME == 'dev' || BRANCH_NAME == 'master' ## condition expression test stage will only execute if branch name is dev or maser ##
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
