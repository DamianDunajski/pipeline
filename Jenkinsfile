#!groovy

properties(
  [[$class: 'GithubProjectProperty', projectUrlStr: 'http://'],
   pipelineTriggers([[$class: 'GitHubPushTrigger']])]
)

node {
   checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/geek-soft/connect-4-game.git']]])
   echo "${env.BRANCH_NAME}"
   echo "${env.getEnvironment()}"
}
