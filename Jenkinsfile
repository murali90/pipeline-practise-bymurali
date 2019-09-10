pipeline{
    agent any 
    stages{
     stage('git checkout'){
         steps {
             checkout([$class: 'GitSCM', 
branches: [[name: '*/master']], 
doGenerateSubmoduleConfigurations: false, 
extensions: [], 
submoduleCfg: [], 
userRemoteConfigs: [[url: 'https://github.com/murali90/maven-project.git']]])
         }
     }
     stage('buid'){
         steps{
             sh 'mvn clean package'
         }
     }
     stage('archiving artifact'){
         steps{
             echo 'archiving artifact'
             archiveArtifacts artifacts: 'webapp/**target/*.war'
         }
     }
     
    }
}
1
