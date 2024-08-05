pipeline {
  agent any
  parameters {
    string defaultValue: 'Test', description: 'Environment to deploy', name: 'Environment', trim: true
    choice choices: ['main', 'dev', 'master'], description: 'Build the pipeline job on particular branch', name: 'Branch'
  }
  stages {
    stage ('BUILD') {
    steps {
      echo "This is build stage"
      sh '''
          echo $Name
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
