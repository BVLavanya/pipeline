pipeline {
  agent any
  stages {
    stage {'BUILD'}
    step {
      echo "This is build stage"
      sh 'sleep 5'
    }
    stage {'DEPLOY'}
    step {
      echo "This is Deploy stage"
      sh 'sleep 5'
    }
    stage {'TEST'}
    step {
      echo "This is Test stage"
      sh 'sleep 5'
    }
  }
}
