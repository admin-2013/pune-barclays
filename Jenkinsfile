currentBuild.displayName = "Artifactory - #"+currentBuild.number
pipeline {
  agent any
   stages {
      stage("CheckOut-SCM"){
          steps{
                      cleanWs()
                      checkout([$class: 'GitSCM',branches: [[name: '*/master']],doGenerateSubmoduleConfigurations: false,extensions: [],submoduleCfg: [],userRemoteConfigs: [[credentialsId: '861a346a-a5a0-4d80-91f5-610cb23f2710',url: 'https://github.com/admin-2013/pune-barclays.git']]])
                }
                     }
       stage("Build"){
           steps{
                    sh label: '', script: 'mvn package'
                   }
             }
             
             stage("archiveArtifacts"){
           steps{
                   archiveArtifacts '**/*.war'
                   }
             }

   }
}
