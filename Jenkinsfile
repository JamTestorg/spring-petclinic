pipeline {
    agent any
    stages {
        stage('build & unit tests') {
            agent {
                label  'build'
            }
            steps {
                withMaven(maven: 'M3', mavenLocalRepo: '.repository') {
                    sh "mvn clean install"
                }
                stash name: "jars", includes: "target/*.jar"
            }
        }
        stage('static-analysis') {
            agent {
                label  'build'
            }
            steps {

            }
        }
        stage('') {
            steps {
                parallel(
                        "chrome": {


                        },
                        "edge": {


                        },
                        "firefox": {

                        }
                )
            }
        }
        stage('staging') {
            steps {
                unstash "jars"
                sh "ls -la target"
            }
        }
        stage('approval') {
            steps {
                input 'Go for it'
            }
        }
        stage('deploy') {
            steps {
                unstash "jars"
                sh "ls -la target"
            }
        }
    }
}
