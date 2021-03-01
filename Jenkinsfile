pipeline {

 environment {
    FULL_IMAGE_NAME = 'cba/nginx-docker'
  }

 stages {

 stage('Docker Build') {
     steps {
       sh 'docker build --pull -t ${FULL_IMAGE_NAME}:${GIT_COMMIT} .'
      }
    }
  }

  stage('Docker Push') {
        when {
          branch 'master'
        }
        steps {
           withDockerRegistry([credentialsId: 'some_user', url: 'some_url']) {
              sh 'docker tag ${FULL_IMAGE_NAME}:${GIT_COMMIT} ${FULL_IMAGE_NAME}:${GIT_COMMIT}'
              sh 'docker push ${FULL_IMAGE_NAME}:${GIT_COMMIT}'
          }
        }
  }

  post {
        always {
            sh "chmod -R 777 ."
            deleteDir()
        }
      }
  }
}