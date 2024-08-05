pipeline {
  agent any
  parameters {
    string defaultValue: 'Test', description: 'Environment to deploy', name: 'Environment', trim: true
    choice choices: ['main', 'dev', 'master'], description: 'Build the pipeline job on particular branch', name: 'Branch'
  }

  environment {
    Deploy_Branch = "$Branch"
    Deploy_Env = "$Environment"
  }
  stages {
    stage ('BUILD') {
    steps {
      echo "Deploying to ${params.Environment}"
      echo "code from branch ${params.$Branch}"
      sh '''
          echo Deploying to ${Environment}
          echo Code from ${Branch} branch
          sleep 5
          exit 0
        '''  
    }
  }
  
    stage ('TEST') {
      parallel {
        stage ('Test with junit') {
          steps {
            echo "Tested with junit"
          }
        }
        stage ('Tested with selenium') {
          steps {
            echo "This is tested with selenium"
          }
        }
      }
    }

    stage ('DEPLOY') {
    steps {
      echo "This is Deploy stage"
      sh '''
         sleep 5
         exit 0
        ''' 
    }
    }
  }
}
