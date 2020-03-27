#!groovy
@Library('logFourJLogger@develop')  _
pipeline {

    agent any

    stages {
        stage ('Compile Stage') {
            steps {   
                script {             
   
                    logInfo("Compile Stage Starting")
                    //logFourJLogger.logInfo("Compile Stage Starting")
                    sh 'mvn clean compile'
                    //logFourJLogger.logInfo("Compile Stage Completed")
                
                }
            }
        }

        stage ('Testing Stage') {
            steps { 
                script {               

                    //logFourJLogger.logInfo("Test Stage Starting")
                    sh 'mvn test'
                    //logFourJLogger.logInfo("Test Stage Completed")
              
                }
            }
        }

    }

}