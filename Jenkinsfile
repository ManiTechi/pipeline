node{
  stage('SCM Pull')
  {
       git(
       url: 'https://github.com/ManiTechi/maninetcore.git',
       credentialsId: 'a08bc7e6-35ae-4148-8e10-c7d5f6fa762a',
       branch: "master"
      )
   }
   stage ('Restore Dependecies') {
        bat 'dotnet restore'
    }
    
    stage ('Build for Error Checks') {
       bat 'dotnet build'
      
    }
    
    stage ('Publish Binaries') {
       bat 'dotnet publish'
        
    }
    
    stage ('Build Docker Image') {
       
    }

}
