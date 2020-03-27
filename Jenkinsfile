#!groovy
@Library('log4Logger@develop')  _
pipeline {

    agent any

    stages {
        stage ('Compile Stage') {
            steps {                
                withMaven(maven: 'maven_3_6_0') {
                    log4Logger.logInfo("Compile Stage Starting")
                    sh 'mvn clean compile'
                    log4Logger.logInfo("Compile Stage Completed")
                }
            }
        }

        stage ('Testing Stage') {
            steps {                
                withMaven(maven: 'maven_3_6_0') {
                    log4Logger.logInfo("Test Stage Starting")
                    sh 'mvn test'
                    log4Logger.logInfo("Test Stage Completed")
                }
            }
        }

    }

}