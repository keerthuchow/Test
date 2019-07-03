node{
    stage ('checkout')
    { 
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '5d6d1f5a-e24e-470e-9163-fcdc7c5903bd', url: 'https://github.com/keerthuchow/Test.git']]])
    }
    stage ('build')
    {
        sh 'mvn clean package'


    }
}