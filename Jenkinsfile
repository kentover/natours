pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing'
            }
        }
        stage('Backup') {
            steps {
                echo 'Backuping'
                sshPublisher(publishers: [sshPublisherDesc(configName: 'agent', 
                transfers: [sshTransfer(cleanRemote: false, excludes: '', 
                execCommand: 'cp -R /var/www/site /var/www/Backup', 
                execTimeout: 120000, 
                flatten: false, makeEmptyDirs: false, 
                noDefaultExcludes: false, 
                patternSeparator: '[, ]+', 
                remoteDirectory: '', 
                remoteDirectorySDF: false, 
                removePrefix: '', 
                sourceFiles: '')], 
                usePromotionTimestamp: false, 
                useWorkspaceInPromotion: false, 
                verbose: false)])
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying'
                sshPublisher(publishers: [sshPublisherDesc(configName: 'agent', 
                transfers: [sshTransfer(cleanRemote: false, excludes: '', 
                execCommand: 'sudo systemctl restart nginx', execTimeout: 120000, 
                flatten: false, 
                makeEmptyDirs: false, 
                noDefaultExcludes: false, 
                patternSeparator: '[, ]+', 
                remoteDirectory: 'site/html/', 
                remoteDirectorySDF: false, 
                removePrefix: '', 
                sourceFiles: '**/*')], 
                usePromotionTimestamp: false, 
                useWorkspaceInPromotion: false, 
                verbose: false)])
            }
        }
    }
}
