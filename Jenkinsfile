node('master') {
  stage('Checkout') {
    deleteDir()
    git credentialsId: 'c3e16041-95c1-4105-a2d6-2835d3aa3b7c', url: 'git@github.com:beeva-josemartinezgonzalez/course-cicd.git'
  }

stage('Test') {
    sh './simplehttpserver/tests/unittests.sh ./simplehttpserver/'
  }

stage('Package and publish') {
    sh "tar -zcvf simplehttpserver-${env.JO_NAME}-${env.BUILD_ID}.tar.gz ./simplehttpserver"
    sh "aws s3 cp simplehttpserver-${env.JOB_NAME}-${env.BUIL_ID}.tar.gz s3://clase-gendevops2-cicd-ci/"
  }

}

