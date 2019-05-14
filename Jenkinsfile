node {
    printMessage("Pipeline Start")

    stage("Fetch Source Code") {
        git 'https://github.com/ravb2019/multipipeline-assignment.git'
    }

    dir('Lesson5/ActivityA') {
        stage("Install Requirements") {
            sh 'make install'
        }

        stage("Run Tests") {
            sh 'make test'
        }

        stage("Deploy") {
            if (env.BRANCH_NAME == "master") {
                printMessage("Deployed to production.")
            } else {
                printMessage("Not deployed to production.")
            }
        }
    }

    printMessage("Pipeline End")
}

def printMessage(message) {
    echo "${message}"
}

