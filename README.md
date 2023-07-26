# The Heroku Buildpack release artifact will no longer be maintained by Metabase, this is a Lopay maintained fork.

# Updating metabase version

1. Update version in /bin/verison
2. Update the Heroku metabase repo (From from heroku git URL): git commit --allow-empty -m "Updated"
3. Push update to Heroku

Clone the latest version to your local machine:
git clone https://github.com/metabase/metabase-deploy.git  
cd metabase-deploy
Add a git remote with your metabase setup:
git remote add heroku https://git.heroku.com/lopay-metabase-production.git
If you are upgrading from a version that is lower than 0.25, add the Metabase buildpack to your Heroku app:
heroku buildpacks:add https://github.com/metabase/metabase-buildpack
Force push the new version to Heroku:
git push -f heroku master
Wait for the deploy to finish




# Heroku Buildpack for Metabase

Add the following to your app.json:

"buildpacks": [
  {
    "url": "https://github.com/metabase/metabase-buildpack"
  }
]
