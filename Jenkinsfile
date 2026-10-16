// Analog of the NERM gem GitHub Actions workflows, running on CloudBees.
// pry-nav tests with Rake, keeps its version in lib/pry-nav/version.rb,
// and does not need Redis or Artifactory to install dependencies.
// A push to master that changes the version file tags the commit and
// publishes the gem. createRelease does the same on demand.

@Library('sailpoint/jenkins-release-utils@CIPLT-954-template-jfrog')_

rubyGemTemplate([
    team                : 'nerm',
    rubyVersion         : '2.7',
    testCommand         : 'bundle exec rake',
    versionConstantFile : 'lib/pry-nav/version.rb',
    enableRedis         : false,
    configureArtifactory: false,
    publishGpr          : false,
    artifactoryGemHosts : 'https://sailpoint.jfrog.io/artifactory/api/gems/sp-gems-prod-local',
    releaseBranches     : ['master','CIPLT-954-template-jfrog'],
])
