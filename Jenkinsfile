pipeline {
    agent { label 'winslave'}

    stages {
        stage('Build') {
            steps {
                bat 'dotnet clean'
                bat 'dotnet build'
            }
        }
        stage('SonarQube analysis') {
            
            steps {
   //   def SONARSCANNER_HOME = tool 'Scanner for MSBuild 2.0'
      withSonarQubeEnv('sonar') {
   
      bat "dotnet ${SONARSCANNER_HOME}\\SonarScanner.MSBuild.dll begin /k:sonar /n:sonar /v:1.0 /d:sonar.host.url=%http://18.206.26.75:9000/sonar/% /d:sonar.login=%835d174e9f3258c2d3046a09e16c396a613e51cc%"
      bat 'dotnet build'
      bat "dotnet ${SONARSCANNER_HOME}\\SonarScanner.MSBuild.dll end"
    }
  }
 }  
}
}
