#!groovy
@Library('logFourJLogger@develop') _
pipeline {

    agent any

    parameters {
	choice(
	    defaultvalue: INFO
            choices: '\nINFO\nDEBUG\nWARN\nERROR',
            description: 'Choose log levels to display in Console Log output. INFO is default. ',
            name: 'env_loglevels')
    }

    stages {
        stage ('Compile Stage') {
            steps {
                script {
                    logWrapper.infomsg("Compile Stage Starting")
                    //logFourJLogger.logInfo()
                    sh 'mvn clean compile'
                    logWrapper.infomsg("Compile Stage Ending")
                    //logFourJLogger.logInfo("Compile Stage Completed")

                }
            }
        }

        stage ('Testing Stage') {
            steps {
                script {
                    logWrapper.infomsg("Test Stage Starting")
                    //logFourJLogger.logInfo("Test Stage Starting")
                    sh 'mvn test'
                    logWrapper.infomsg("Test Stage Ending")
                    //logFourJLogger.logInfo("Test Stage Completed")

                }
            }
        }

    }

}
