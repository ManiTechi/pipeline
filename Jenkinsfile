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
       bat 'docker build -t maninetcore/api-gen .'
    }
    
  stage('Push Docker Image')
  {
    // withDockerRegistry([ credentialsId: "034ea55d-85e4-42ca-96d5-69a268bfbcdb", url: "https://hub.docker.com" ]) {
     //     bat 'docker push maninetcore/api-gen'
       // }
    
     bat 'docker login --username manidockerhub --password Test!10051982'
     bat 'docker push maninetcore/api-gen'
  }
  
  stage('Run Docker Machine')
  {
     sh 'docker run --rm -it maninetcore/api-gen'
  }

}
