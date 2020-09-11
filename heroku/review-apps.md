# Review Apps

## Objective

The Review Apps Heroku Pipeline would allow one not to have to use the Heroku remote to push to the staging server on Heroku. Overall, this should allow one to increase workload capacity since the Review Apps Pipeline could cut out the learning curve of deploying to Heroku via the Heroku remote through the CLI.

Heroku deploys the HEAD commit of the branch that the associated Pull Request is created on. When the branch is updated Heroku redeploys to the connected repo on the Review Apps Pipeline with your latest commit.

In summary, this guide will help you have a better understanding of what Review Apps on Heroku does and how to set it up for your GitHub repo.

#### Technologies Discussed

* Heroku
* Review Apps Pipeline

#### Setting Up Review Apps Steps

1.Create a Pipeline by going to your Heroku dashboard, going to `new`, clicking the dropdown, and clicking on `create new Pipeline`

![create new pipeline](https://tk-assets.lambdaschool.com/fbc62d5d-ea11-4976-bd98-c8294305f2fe_ScreenShot2020-05-07at3.43.16PM.png)

2.Make sure to add the repo you want to connect the Review Apps Pipeline to

![connect repo to pipeline](https://tk-assets.lambdaschool.com/a6312cb5-6b39-42db-be84-724d05881acc_ScreenShot2020-05-07at3.48.55PM.png)

3.Once on the Pipeline Dashboard click `Enable Review Apps`

![enable review apps](https://tk-assets.lambdaschool.com/e148df1f-653b-4f43-a3ac-0317e233997a_ScreenShot2020-05-07at3.53.22PM.png)

4.Then config Reviews Apps with your preferred settings

* `Automatically create review apps for new PRs`
* `Destroy stale review apps automatically` - set to preferred time frame

![config pipeline](https://tk-assets.lambdaschool.com/0f2e4a39-c47d-4a07-baaf-c19d12e68ff5_ScreenShot2020-05-07at3.57.09PM.png)

#### References

For more information about setting up Review Apps on Heroku click [here](https://devcenter.heroku.com/articles/github-integration-review-apps#configuration)

