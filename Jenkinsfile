node{
  stage('SCM Pull')
  {
       git(
       url: 'https://github.com/ManiTechi/maninetcore.git',
       credentialsId: 'a08bc7e6-35ae-4148-8e10-c7d5f6fa762a',
       branch: "master"
      )
   }
   stage('Restore Package')
   {
       dotnet restore
   }
}
