#!groovy
/*
    This is an sample Jenkins file for demo.
 */
 
pipeline {
  agent { label 'master' }
  stages {

     stage('Builds') {
      parallel {
        stage("Cypress build") {
          stages {
            stage("Cypress (build)") {
              agent any
              steps {
                echo "Inside for loop 4"
              }
            }
          }
        }
        stage("selenium build") {
          stages {
            stage("selenium (build)") {
              agent any
              steps {
                echo "Inside for loop 2"
              }
            }
          }
        }
      }
    }

     stage ('behat') {
       agent any
       steps {
        echo "behat"
       }
    }

    stage ('prepare test') {
       agent any
       steps {
        echo "prepare test"
       }
    }

    stage ('api') {
       agent any
       steps {
        echo "api"
       }
    }

    stage('Web test (Behat & Cypress)') {
      parallel {
        stage("Behat") {
          stages {
            stage("Behat (web)") {
              agent any
              steps {
                echo "Inside for loop 2"
              }
            }
          }
        }
        stage("Cypress") {
          stages {
            stage('Stage 2') {
                steps {
                    script {
                        parallel (
                            "Stage 2.1.": {
                                echo "Stage 2.1."
                            },
                            "Stage 2.2.": {
                                echo "Stage 2.2."
                            }
                        )
                    }
                }
            }
          }
        }
      }
    }

  }
}

