pipeline {
    agent { label 'winslave'}

    stages {
        stage('Build') {
            steps {
                bat 'dotnet clean'
                bat 'dotnet build'
            }
        }
        
      //  stage ('Junit') {
        //    steps {
          //     dir(path: )
        stage('SonarQube analysis') {
            
            steps {
     def SONAR_HOME = tool 'sonar'
      withSonarQubeEnv('sonar') {
   
          bat "dotnet ${SONAR_HOME}\\SonarScanner.MSBuild.dll begin /k:winjenkins21_demo_master-MJEISRAJXWZZ3Y64VW2AXY3RWQMTXWIURLBNSJZ3Z624JVO3IQLA /n:winjenkins21_demo_master-MJEISRAJXWZZ3Y64VW2AXY3RWQMTXWIURLBNSJZ3Z624JVO3IQLA /v:1.0 /d:sonar.host.url=http://18.206.26.75:9000/sonar/ /d:sonar.login=835d174e9f3258c2d3046a09e16c396a613e51cc"
          bat 'dotnet build'
          bat "dotnet ${SONAR_HOME}\\SonarScanner.MSBuild.dll end"
    }
  }
 }  
}
}
