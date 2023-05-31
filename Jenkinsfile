pipeline {
    triggers {
  pollSCM('* * * * *')
    }
   agent any
    tools {
  maven 'M2_HOME'
}
    stages {
        stage('Checkout'){
            steps{
                git branch: 'main', url: 'https://github.com/Yn-Olvr/fastfoodtest.git'
            }
        }
        stage('Code Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
       // stage("build & SonarQube analysis") {          
           // steps {
              //  dir('./fastfood_BackEnd/'){
               //     withSonarQubeEnv('SonarServer') {
                  //      sh 'mvn verify org.sonarsource.scanner.maven:sonar-maven-plugin:sonar -Dsonar.projectKey=Yn-Olvr_fastfoodtest'
                      //  }
               // }
            //}
          }
    }
}