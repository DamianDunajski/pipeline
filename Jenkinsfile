#!groovy

properties(
  [[$class: 'GithubProjectProperty', projectUrlStr: 'http://'],
   pipelineTriggers([[$class: 'GitHubPushTrigger']])]
)

node {
   checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/geek-soft/connect-4-game.git']]])
   echo "${env.BRANCH_NAME}"
   echo "${env.getEnvironment()}"
   echo "${currentBuild}"
   echo "${currentBuild.rawBuild}"

   def changeLogSets = currentBuild.rawBuild.changeSets
   echo "${changeLogSets}"
for (int i = 0; i < changeLogSets.size(); i++) {
    def entries = changeLogSets[i].items
    for (int j = 0; j < entries.length; j++) {
        def entry = entries[j]
        echo "${entry.commitId} by ${entry.author} on ${new Date(entry.timestamp)}: ${entry.msg}"
        def files = new ArrayList(entry.affectedFiles)
        for (int k = 0; k < files.size(); k++) {
            def file = files[k]
            echo "  ${file.editType.name} ${file.path}"
        }
    }
}
}
