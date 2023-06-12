
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
                synopsys_detect "--detect.docker.passthrough.service.timeout=\"120\" --detect.cleanup=true --detect.project.name=\"Test Project\" --blackduck.offline.mode=true --logging.level.com.synopsys.integration=TRACE"
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