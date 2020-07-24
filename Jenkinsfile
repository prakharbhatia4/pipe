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
              stage('Build Stage') {
                               steps{
                                        bat 'mvn -version'
                                     }
                                    }
              stage('Compile Stage'){
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
                                                                     bat 'mvn clean package sonar:sonar'
                                                                 } 
                                      } 
                                    }
        stage('Deploy artifact'){
                                steps{
                                     bat 'deploy'
                                      }
                                     }   
      
      
      
              
  }
}

