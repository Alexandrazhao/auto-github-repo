# auto-github-repo

This pipeline provides an easiler way to create github repos with some file templates in them. Once the build successes, buildkite will send user an email as notificaion.

## What you need in this pipeline
1. Github Personal Access Token (This token should be securely saved through Buildkite secrets storage).
2. Come up with a name for you repo.


## How does this work
1. Add a new pipeline to Buildkite, link this auto-github-repo to your new created pipeline. 
2. Save your Github access token as environment variables (This is not a safe way though). eg: ```GITHUB_MY_APP_DEPLOYMENT_ACCESS_TOKEN=my_github_token```
3. Set ```MY_REPO=NAME``` in environment variables.
4. Set ```buildkite-agent pipeline upload .buildkite/pipeline.yaml``` in Commands to run, ```queue=lightweight``` as Agent Targeting Rules, then save the steps. 

## Build your pipeline!
1. Click ```New Build```, type any message you like, then click ```Create Build```. Buildkite will ask you to ```Name Your Repo```, enter the repo name you like, make sure you don't use repeated name because it is not allowed to create the same name repo in github. After the build is done, buildkite will send you an email to inform you. Then your newly repo will appear in your Github! 
