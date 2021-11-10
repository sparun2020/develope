pipeline {
    agent any
    tools {
     maven 'Maven 3.8.3'   
    }
   
    stages {
        stage('Build') {
            steps {
                echo 'Hi Arun KUmar Parvathy - Welcome to the new world'
                            }
        }
        stage('Test') {
            steps {
                   echo "Run --->" 
                   sh 'mvn --version'
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
                    sh 'mvn --version'
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
