node{
    stage ('checkout')
    { 
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '5d6d1f5a-e24e-470e-9163-fcdc7c5903bd', url: 'https://github.com/keerthuchow/Test.git']]])
    }
    stage ('build')
    {
        def mvn_version = 'M3'
        withEnv( ["PATH+MAVEN=${tool mvn_version}/bin"] )
        {
                sh "mvn clean package"
        }
    }
    stage('code coverage')
    
    {
        jacoco deltaBranchCoverage: '40', deltaClassCoverage: '50', deltaComplexityCoverage: '50', deltaInstructionCoverage: '50', deltaLineCoverage: '50', deltaMethodCoverage: '50', maximumBranchCoverage: '88', maximumClassCoverage: '80', maximumComplexityCoverage: '90', maximumInstructionCoverage: '90', maximumLineCoverage: '80', maximumMethodCoverage: '70', minimumBranchCoverage: '80', minimumClassCoverage: '75', minimumComplexityCoverage: '88', minimumInstructionCoverage: '75', minimumLineCoverage: '77', minimumMethodCoverage: '65'
   
   }
}