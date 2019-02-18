// vi: ft=groovy
// this is a scripted pipeline, NOT a dsl script pipeline
node {
  stage('pull code') {
   
  }
  stage('prebuild') {
    echo "Running the prebuild stage"
    sh 'env'
  }
  stage('build') {
    echo "Running the build stage"
  }
  stage('test'){
    echo "Running the test stage"
  }
  stage('archive'){
    echo "Running the archive stage"
  }
  stage('deploy'){
    echo "Running the deploy stage"
    if (currentBuild.result == 'SUCCESS') { // <1>
      echo "Build status and test status is good deploying "
    }
    else {
      echo "Current build status is unstable not deploying"
    }
  }
  stage('cleanup'){
    echo "Running the cleanup stage"
  }

}
