pipeline {
    agent { label 'winslave'}

    stages {
        stage('Build') {
            steps {
                script {
                bat 'dotnet clean'
                bat 'dotnet build'
            }
        }
    
       }
    
      // stage ('sonar') {
      //      steps {
      //          script { 
      //              def scannerhome=tool 'sonar'
      //              withSonarQubeEnv {'sonar'} {
      //                  bat 'scannerhome/bin/sonar-scanner'
      //              }
      //          }
      //      }
                    
      //  }         
   // }
// }
    
    //    stage('Sonar') {
            
            // steps {
            //    script {
           //         powershell(returnStdout: true, script: '.\\sonar.ps1')
         //       }
        //    }
      //  }
        stage ('sonar') {
            steps {
                
                
      def SONAR_HOME = tool 'sonar'
      withSonarQubeEnv('sonar') {
   
          bat 'dotnet  ${SONAR_HOME} begin /k:cjptest123_demo_master-6SVISBM64JK3DRBKPFNHODJJ5RBWM7HLXUCAYNCGDDEK2KFLN3VQ /n:cjptest123_demo_master-6SVISBM64JK3DRBKPFNHODJJ5RBWM7HLXUCAYNCGDDEK2KFLN3VQ /v:1.0 /d:sonar.host.url=http://13.57.35.130:9000/sonar/ /d:sonar.login=a53ad0ff4ba5fd8ba3c97e8f686a2e18a53d048a'
      bat 'dotnet build'
          bat 'dotnet ${SONAR_HOME}  end'
    }
       

  }
 }  
}
}
