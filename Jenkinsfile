pipeline  {
   agent any
tools{
     jdk 'jdk1.8'
     maven 'maven3.6'
}

 
   stages {
  
  
      
              stage("Code Checkout") {
                                steps {
                                       git url: 'https://github.com/prakharbh4/pipe.git'
                                      }
                                     }
    
              stage('Build Stage'){
                                steps{
                                       bat 'mvn clean install'
                                      }
                                     }
              stage('Testing Stage'){
                                steps{
                                      bat 'mvn test'
                                     } 
                                    }
              stage('build && SonarQube analysis'){
                                steps {
                                       withSonarQubeEnv('sonar') {
                                                                     bat 'mvn sonar:sonar'
                                                                 } 
                                      } 
                                    }
              stage('Deploy artifacts'){
                                steps{
                                       bat 'mvn deploy'
                                      }
                                     }   
      
      
      
              
  }
}

