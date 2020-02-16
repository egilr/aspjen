pipeline {
   agent any
   stages {
      stage('Build') {
         steps {
            bat 'dotnet build'
         }
      }
      stage('Test') {
         steps {
            bat 'dotnet test'
         }
      }
      stage('Publish') {
         steps {
            bat 'dotnet publish aspjen.csproj -o publish -c Release -r win-x64 /p:PublishSingleFile=true'
         }
      }
      stage('Dir') {
         steps {
            bat 'dir'
         }
      }
   }
}
