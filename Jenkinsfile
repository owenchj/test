  pipeline {
        agent any
        stages{
            stage("Compile") {
                steps {
                    script {
                        echo "Compiling..."
                    }
                }
            }
            stage("Test") {
                steps {
                    script {
                        echo "Testing..."
                    }
                }
            }
            stage("Build") {
                steps {
                withCredentials([sshUserPrivateKey(credentialsId: 'jenkins_test', keyFileVariable: 'SSH_KEY')]) {
                sh("echo $SSH_KEY > my_file")
                sh("cat my_file")
                sh("git push origin master")
                }
                }
            }
        }
    }
