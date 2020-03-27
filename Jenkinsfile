#!groovy
@Library('log4Logger@develop')  _
pipeline {

    agent any

    stages {
        stage ('Compile Stage') {
            steps {   
                script {             
   
                    log4Logger.logInfo("Compile Stage Starting")
                    sh 'mvn clean compile'
                    log4Logger.logInfo("Compile Stage Completed")
                
                }
            }
        }

        stage ('Testing Stage') {
            steps { 
                script {               

                    log4Logger.logInfo("Test Stage Starting")
                    sh 'mvn test'
                    log4Logger.logInfo("Test Stage Completed")
              
                }
            }
        }

    }

}