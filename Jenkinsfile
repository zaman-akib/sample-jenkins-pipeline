
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
        stage('SCA and Vulnerability Scan') {
            steps {
                echo 'SCA AND VULNERABILITY SCAN STARTED'
                synopsys_detect "--blackduck.url=https://sig-bd-hub.app.blackduck.com " +
                "--blackduck.api.token=YTllMTE2ODgtMjQ2YS00MTU0LTkxNDMtYmEyYjZlNWJmNTA4OmI2NzRlN2Y3LTIzZWQtNDcxOC04Y2IzLWI1YzFhMjY2MWUwYw== " +
                "--detect.docker.passthrough.service.timeout=120 --detect.cleanup=true " +
                "--detect.project.name=\"Test Project\""
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