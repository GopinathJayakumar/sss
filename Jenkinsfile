pipeline {
  agent any
  stages {
    stage('Development Evn') {
      steps {
        echo 'Make a Connection with your SCM(git))'
        echo 'Pull the code from your Connected Repo'
        echo 'Build the Code in your Local'
      }
    }

    stage('Smoke Testing') {
      steps {
        echo 'Run 5 Smoke Tests'
      }
    }

    stage('Deploy QA Evn') {
      steps {
        echo 'Stop the Server'
        echo 'Move the new Build from Dev to QA Env'
      }
    }

    stage('Integration Testing') {
      parallel {
        stage('Integration Testing') {
          steps {
            echo 'UI Test - Integration'
          }
        }

        stage('Api Testing') {
          steps {
            echo 'Using REST Call - Automation Testing'
          }
        }

        stage('Performance Testing') {
          steps {
            echo 'Using Loadrunner / Jmeter Testing'
          }
        }

      }
    }

    stage('Certify') {
      steps {
        echo 'QA - Certify'
      }
    }

  }
}