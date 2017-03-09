#!groovy

properties(
  [[$class: 'GithubProjectProperty', projectUrlStr: 'http://'],
   pipelineTriggers([[$class: 'GitHubPushTrigger']])]
)

node {
   stage('Checkout') {
    checkout scm

    echo "${env.BRANCH_NAME}"
    echo "${env.getEnvironment()}"
   }
}
