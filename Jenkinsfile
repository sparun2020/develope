pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Hi Arun KUmar Parvathy - Welcome to the new world'
            }
        }
        stage('Test') {
            steps {
                   echo "Run --->" 
            }
        }
        stage('Deploy') {
            when {
                  not
                     {
                       branch "master"
                  }
            }
            steps {
                    echo "Run"
            }

        }
        stage('Parallel Run') {
                                parallel {
                                      stage('Unit Test') {
                                          steps {
                                             echo "running the unit"
                                          }

                                      }

                                       stage('Integration Test') {
                                                     agent {
                                                         docker {
                                                                 reuseNode false
                                                                 image 'ubuntu'
                                                          }
                                                       }
                                                      steps {
                                                          echo "Running Integration Test"
                                                      }
                                        }

                                 }


        }




    }
}
