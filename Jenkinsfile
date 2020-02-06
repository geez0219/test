pipeline {
  agent any
  stages {
    stage('Test') {
        steps {
            sh '''
                export PATH=/home/ubuntu/anaconda3/bin:$PATH
                echo $PATH
                conda create --name jenkins-env python=3.6 
            '''
        }
        
        steps{
            sh '''
                echo $PATH
            '''
        }
    }

  }
}
