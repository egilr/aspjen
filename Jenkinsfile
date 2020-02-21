pipeline {
   agent any
   stages {
   stage('Git') {
            steps {
                step([$class: 'WsCleanup'])
                checkout scm
            }
        }
/*
        stage('WSCleanup') {
            steps {
            echo '----------------------------------------------------------------------------'
            echo 'WSCleanup'
            echo '----------------------------------------------------------------------------'
            step([$class: 'WsCleanup'])
            }
        }
*/
      stage('Build') {
         steps {
            echo '----------------------------------------------------------------------------'
            echo 'Build'
            echo '----------------------------------------------------------------------------'
            bat 'dotnet build'
         }
      }
      stage('Test') {
         steps {
            echo '----------------------------------------------------------------------------'
            echo 'Test'
            echo '----------------------------------------------------------------------------'

            bat 'dotnet test'
         }
      }
      stage('Publish') {
         steps {
            echo '----------------------------------------------------------------------------'
            echo 'Publish'
            echo '----------------------------------------------------------------------------'

            bat 'dotnet publish aspjen.csproj -o publish -c Release -r win-x64 /p:PublishSingleFile=true'
         }
      }
      stage('Dir') {
         steps {
            echo '----------------------------------------------------------------------------'
            echo 'Dir'
            echo '----------------------------------------------------------------------------'
            bat 'Dir'
         }
      }
      stage('Mail') {
         steps {
            echo '----------------------------------------------------------------------------'
            echo emailext body: 'Testing..', subject: 'Testing....', to: 'egil.larsen@dk.ibm.com'
            echo '----------------------------------------------------------------------------'
            bat 'Dir'
         }
      }

   }
}
