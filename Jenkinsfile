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
        stage ('Sonar') {
            steps {
                script { 
                    def scannerhome=tool 'Sonar'
                    withSonarQubeEnv {'Sonar'} {
                        bat 'scannerhome/bin/sonar-scanner'
                    }
                }
            }
                    
        }         
    }
    
        //stage('Sonar') {
            
            // steps {
            //    script {
           //         powershell(returnStdout: true, script: '.\\sonar.ps1')
         //       }
        //    }
      //  }
     // def SONAR_HOME = tool 'sonar'
     // withSonarQubeEnv('sonar') {
   
       //   bat '%dotnet%  %{SONAR_HOME}% %begin% /k:'winjenkins21_demo_master-MJEISRAJXWZZ3Y64VW2AXY3RWQMTXWIURLBNSJZ3Z624JVO3IQLA' /n:'winjenkins21_demo_master-MJEISRAJXWZZ3Y64VW2AXY3RWQMTXWIURLBNSJZ3Z624JVO3IQLA' /v:'1.0' /d:sonar.host.url=http://18.206.26.75:9000/sonar/ /d:sonar.login='835d174e9f3258c2d3046a09e16c396a613e51cc''
      //bat '%dotnet% %build%'
    //      bat '%dotnet% %{SONAR_HOME}%  %end%'
   // }
          //`      }
}
  //}
 //}  
//}
//}
