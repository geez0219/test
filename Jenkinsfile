pipeline {
  agent any
  stages {
    stage('Test') {
        steps {
            sh './install_dependency.sh'
        }
    }
    
    stage('Test2') {
        steps{
            sh '''
                echo $PATH
            '''
        }
    }
  }
}
