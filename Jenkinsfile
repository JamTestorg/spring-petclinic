pipeline {
    agent any
    stages {
        stage('build & unit tests') {
            agent {
                label  'build'
            }
            steps {
                sleep '5'
            }
        }
        stage('static-analysis') {
            agent {
                label  'build'
            }
            steps {
                sleep '5'
            }
        }
        stage('') {
            steps {
                parallel(
                        "chrome": {
                            sleep '5'

                        },
                        "edge": {
                            sleep '5'

                        },
                        "firefox": {
                            sleep '5'

                        }
                )
            }
        }
        stage('staging') {
            steps {
                sleep '5'
            }
        }
        stage('approval') {
            steps {
                input 'Go for it'
            }
        }
        stage('deploy') {
            steps {
                sleep '5'
            }
        }
    }
}
