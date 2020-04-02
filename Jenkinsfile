#!groovy
@Library('callLog@develop') _
pipeline {

    agent any

    parameters {
        extendedChoice (
            defaultValue: 'INFO', 
            description: 'Select the log levels to display in Console Log. INFO is default',
            multiSelectDelimiter: ',', name: 'env_loglevel', quoteValue: false, 
            saveJSONParameterToFile: false, 
            type: 'PT_MULTI_SELECT', 
            value: 'INFO,DEBUG,WARN,ERROR', 
            visibleItemCount: 4
        )
    }

    stages {
        stage ('Compile Stage') {
            steps {
                script {
                    callLog()
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {
            steps {
                script {
                    sh 'mvn test'
                }
            }
        }

    }

}
