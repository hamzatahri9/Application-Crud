pipeline {
    agent any 
      
     environment {
            CI = 'true'
        }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
                echo 'build the application...'
            }
        }
        stage('Test') {
                    steps {
                        sh './jenkins/scripts/test.sh'
                        echo 'testing the application'
                    }
                }
                stage('Deliver') {
                            steps {
                                sh './jenkins/scripts/deliver.sh'
                                echo 'Finished using the web site? (Click "Proceed" to continue)'
                                sh './jenkins/scripts/kill.sh'
                            }
                        }

    }
}
