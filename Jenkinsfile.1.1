#!/usr/bin/env groovy

node {
    env.PATH = "C:\\Program Files (x86)\\Git\\usr\\bin;C:\\Program Files (x86)\\Git\\bin;${env.PATH}"
    // stage('checkout') {
    //     checkout scm
    // }

    // stage('check java') {
    //     sh "java -version"
    // }

    // stage('clean') {
    //     sh "chmod +x gradlew"
    //     sh "./gradlew clean --no-daemon"
    // }

    // stage('npm install') {
    //     sh "./gradlew npm_install -PnodeInstall --no-daemon"
    // }

    // stage('backend tests') {
    //     try {
    //         sh "./gradlew test integrationTest -PnodeInstall --no-daemon"
    //     } catch(err) {
    //         throw err
    //     } finally {
    //         junit '**/build/**/TEST-*.xml'
    //     }
    // }

    // stage('frontend tests') {
    //     try {
    //         sh "./gradlew npm_run_test -PnodeInstall --no-daemon"
    //     } catch(err) {
    //         throw err
    //     } finally {
    //         junit '**/build/test-results/TESTS-*.xml'
    //     }
    // }

    // stage('packaging') {
    //     sh "./gradlew bootJar -Pprod --no-daemon"
    //     archiveArtifacts artifacts: '**/build/libs/*.jar', fingerprint: true
    // }

    stage ('Deploy') {
            steps {

                withCredentials([[$class          : 'UsernamePasswordMultiBinding',
                                  credentialsId   : 'PCF_LOGIN',
                                  usernameVariable: 'USERNAME',
                                  passwordVariable: 'PASSWORD']]) {

                    sh '/usr/local/bin/cf login -a http://api.run.pivotal.io -u $USERNAME -p $PASSWORD'
                    // sh '/usr/local/bin/cf push'
                    sh 'cf push -b https://github.com/cloudfoundry/java-buildpack.git -f ./deploy/cloudfoundry/manifest.yml -p ./build/libs/store-0.0.1-SNAPSHOT.jar'
                }
            }

        }
  
}
