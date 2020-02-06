pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''
            ANACONDA_DIR=/home/ubuntu/anaconda3
            JENKINS_ENV_DIR=/var/lib/jenkins/.conda/envs
            ENV_NAME=pr_env
            
            . $ANACONDA_DIR/etc/profile.d/conda.sh
            if [ ! -d "$JENKINS_ENV_DIR/$ENV_NAME" ]; then
                conda create --name $ENV_NAME python=3.6 -y
            fi
            conda activate $JENKINS_ENV_DIR/$ENV_NAME 
            which python
            which pip
            pip install pytest 

        '''
      }
    }
    stage('Test') {
        steps {
            sh '''
                ANACONDA_DIR=/home/ubuntu/anaconda3
                JENKINS_ENV_DIR=/var/lib/jenkins/.conda/envs
                ENV_NAME=pr_env
                
                . $ANACONDA_DIR/etc/profile.d/conda.sh
                conda activate $JENKINS_ENV_DIR/$ENV_NAME
                which python 
                which pip
                python -m pytest
            '''
        }
    }
  }
}
