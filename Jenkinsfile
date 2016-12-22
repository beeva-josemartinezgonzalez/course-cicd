node('master') {
  stage('Checkout') {
    deleteDir()
    git credentialsId: 'c3e16041-95c1-4105-a2d6-2835d3aa3b7c', url: 'git@github.com:beeva-josemartinezgonzalez/course-cicd.git'
  }
}

stage('Test') {
    sh './simplehttpserver/tests/nittests.sh ./simplehttpserver/'
  }

