pipeline {
  agent any
  parameters {
      string(name: 'VERSION', defaultValue: '', description: 
      choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: ' ')
      booleanParam(name: 'executeTests', defaultValue: true, description: '')
             
  }
  stages {
  
    stage("build") {
      steps {
        echo 'building the application'
      }
    }
    stage("test") {
      when {
        expression {
            /BRANCH_NAME == 'dev' || BRANCH_NAME == 'dev' && CODE_CHANGES == true
            params.executeTests
        }
          }
      steps {
        echo 'testing the application'
      }
    }
    stage("deploy") {
      steps {
        echo 'deploying the application ...'
        echo "deploying version ${params.VERSION}"
      }
    }
  }
}
/*post {
  always {
    //
  }
  failure {
  }*/
}
