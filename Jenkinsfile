
pipeline {
    agent any

    stages {
         stage('1-Build') {
              steps {
                   echo "Start of stage build"
                                  echo "Building...."
                                  echo "End of building"
              }
         }
         stage('1-Test') {
             steps {
                  echo "Start of stage test"
                                 echo "testing"
                                 echo "end of testing"
             }
         }
         stage('3-Deploy') {
             steps {
                 echo "start of deploying"
                                 echo "Deploying"
                                 echo "end of deploying"
             }
         }
    }
}
