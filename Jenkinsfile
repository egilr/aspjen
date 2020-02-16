pipeline {
   agent any
   stages {
      stage('Build') {
         steps {
            bat 'dotnet build'
         }
      }
      stage('Publish') {
         steps {
            bat 'dotnet publish -o publish -c Release -r win-x64 /p:PublishSingleFile=true'
         }
      }
      stage('Dir') {
         steps {
            bat 'dir'
         }
      }
   }
}