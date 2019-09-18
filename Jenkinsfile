#!/usr/bin/env groovy
pipeline {

    agent any
    environment { 
        PATH = "C:\\Program Files (x86)\\Git\\usr\\bin;C:\\Program Files (x86)\\Git\\bin;${PATH}"
    }
    stages {

        // stage ('Build') {
        //     steps {
        //         withMaven(maven: 'maven_3_5_0') {
        //             sh 'mvn clean package'
        //         }
        //     }
        // }

        stage ('Deploy') {
            steps {

                withCredentials([[$class          : 'UsernamePasswordMultiBinding',
                                  credentialsId   : 'PCF_LOGIN',
                                  usernameVariable: 'USERNAME',
                                  passwordVariable: 'PASSWORD']]) {

                    sh 'cf login -a http://api.run.pivotal.io -u $USERNAME -p $PASSWORD'
                    // sh '/usr/local/bin/cf push'
                    sh 'cf push -b https://github.com/cloudfoundry/java-buildpack.git -f ./deploy/cloudfoundry/manifest.yml -p ./build/libs/store-0.0.1-SNAPSHOT.jar'
                }
            }

        }

    }

}
