pipeline{
  
// all pipeline code will be written here
// declarative   key 'value'
tools{
    // this section is not mandatory
    maven 'mymaven'
    
}

agent  any  // this section is mandatory, here any = current controller

stages{
    // here we will write the job names and stesp to be executed by jenkins
    // we can create many stage, each stage is like a job it will have a unique name
  
  stage('Checkout Code')  
    {
        steps{
            
            git 'https://github.com/Sonal0409/Jenkinsfile-Demo-pipleineCode.git'
        }
        
    }
    stage('Code Review')  
    {
        steps{
            sh 'mvn pmd:pmd'
        }
        
    }
     stage('Code Test')  
    {
        steps{
            sh 'mvn test'
        }
         post{
            success{
                junit stdioRetention: '', testResults: 'target/surefire-reports/*.xml'
            }
        }
    }
     stage('package')  
    {
        steps{
            sh 'mvn package'
        }
        
    }
}
    
}
