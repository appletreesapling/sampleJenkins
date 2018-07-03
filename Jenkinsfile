// vi: ft=groovy
// this is a scripted pipeline, NOT a dsl script pipeline
node {
  stage('pull code') {
    // pull the code to the workspace
    checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '02e843ff-9bd8-47e3-8c95-0a06976d594e', url: 'https://github.com/GSD-development/sampleJenkins.git']]])
     echo "My branch is: ${env.BRANCH_NAME}"
     sh ' echo in sh: $BRANCH_NAME'
     echo "The Build num: ${env.BUILD_NUMBER}"
  }
  stage('prebuild') {
    echo "Running the prebuild stage"
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
