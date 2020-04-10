#!groovy
@Library('testJenkinsShare@develop') _
pipeline {

    agent any

    parameters {
        extendedChoice (
            defaultValue: 'INFO', 
            description: 'Choose the log levels to display in Console Log. INFO level is default.', multiSelectDelimiter: ',', 
            name: 'env_loglevel', 
            quoteValue: false, 
            saveJSONParameterToFile: false, 
            type: 'PT_CHECKBOX', 
            value: 'INFO, DEBUG, WARN, ERROR', 
            visibleItemCount: 4
        )
    }

    stages {
        stage ('Compile Stage') {
            steps {
                script {
                    //callLog.testOne()

                    Foo.call()
                    sh 'javac HelloWorld.java'
                }
            }
        }

        stage ('Testing Stage') {
            steps {
                script {
                    println "THIS IS A TEST"
                }
            }
        }

    }

}
