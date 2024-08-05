pipeline {
  agent any
  stages {
    stage ('BUILD') {
    steps {
      echo "This is build stage"
      sh '''
          sleep 5
          exit 0
        '''  
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
  }
}
