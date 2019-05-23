#!/usr/bin/env groovy

pipeline {
    agent any
    stages {
        stage('Build') {
            when {
                expression {
                    openshift.withCluster() {
                        return !openshift.selector('bc', 'ilivalidator-web-service').exists();
                    }
                }
            }
            steps {
                script {
                    openshift.withCluster() {
                        openshift.withProject('test') {
                            //openshift.newBuild("--name=ilivalidator-web-service"https://github.com/sogis/ilivalidator-web-service.git)
                        }
                    }
                }
            }
        }
    }
}
