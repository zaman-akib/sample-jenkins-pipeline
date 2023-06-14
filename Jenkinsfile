
pipeline {
    // install golang 1.14 on Jenkins node
    agent any
    stages {
        stage("unit-test") {
            steps {
                echo 'UNIT TEST EXECUTION STARTED'
            }
        }
        stage("functional-test") {
            steps {
                echo 'FUNCTIONAL TEST EXECUTION STARTED'
            }
        }
        stage("code-analysis") {
            steps {
                echo 'CODE ANALYSIS EXECUTION STARTED'
                code_analysis param2: 'BLOCKING', param1: 'BLACK_DUCK'
            }
        }
        stage("build") {
            steps {
                echo 'BUILD EXECUTION STARTED'
                echo 'Pulling...' + env.BRANCH_NAME
                hello_world name: 'Akib'
            }
        }
    }
}