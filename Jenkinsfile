pipeline {
  agent any
  stages {
    stage('Test') {
        steps {
            sh '''
              ANACONDA_DIR=/home/ubuntu/anaconda3
              JENKINS_ENV_DIR=/var/lib/jenkins/.conda/envs
              export ENV_NAME=pr_env

              export PATH=$ANACONDA_DIR/bin:$PATH
              if [ ! -d "$JENKINS_ENV_DIR/$ENV_NAME" ]; then
                conda create --name $ENV_NAME python=3.6 -y
              fi

              . $ANACONDA_DIR/etc/profile.d/conda.sh
              conda activate $ENV_NAME

              pip install pytest 
            '''
        }
    }
    
    stage('Test2') {
        steps{
            sh '''
                echo $ENV_NAME
            '''
        }
    }
  }
}
