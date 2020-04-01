#!groovy
@Library('logFourJLogger@develop') _
pipeline {

    agent any

    parameters {
	extendedChoice (defaultValue: 'INFO', 
	description: 'Select the log levels to display in Console Log. INFO is default',
	multiSelectDelimiter: ',', name: 'env_loglevel', quoteValue: false, 
	saveJSONParameterToFile: false, 
	type: 'PT_MULTI_SELECT', 
	value: 'INFO,DEBUG,WARN,ERROR', 
	visibleItemCount: 4)
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
