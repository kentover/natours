
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
                 sshPublisher(publishers: [sshPublisherDesc(configName: 'mywebserver',
                 transfers: [sshTransfer(cleanRemote: false, excludes: '',
                 execCommand: 'echo \'finish\'',
                 execTimeout: 120000,
                 flatten: false,
                 makeEmptyDirs: false,
                 noDefaultExcludes: false,
                 patternSeparator: '[, ]+',
                 remoteDirectory: '/var/www/html',
                 remoteDirectorySDF: false,
                 removePrefix: '',
                 sourceFiles: '**')],
                 usePromotionTimestamp: false,
                 useWorkspaceInPromotion: false,
                 verbose: false)])
             }
         }
    }
}
