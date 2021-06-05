pipeline {
        agent any
        stages {
            stage('Build') {
            steps {
                echo 'Hi , this is our build step'

            }
        }

            stage('Test') {
            steps {
                echo 'this is our testing step'

            }
            
        }

            stage('Deploy') {
            parallel {
                stage('Start Deploy') {   
                steps {
                    echo  " We are starting docker doployment" 
                }
                }
                stage('Deploying now') {
                agent {
                    docker {
                        reuseNode true 
                        image 'nginx'
                    }
                }
                step {
                    echo "we have completed Deployment"
                }
                }
            }

            steps {
                echo 'this is our deployment stage'

            }
        }
    }
}
