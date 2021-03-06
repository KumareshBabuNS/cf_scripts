# MySQL Tile Test

This script will perform the following:

1.  login to a foundation/org/space
1.  create an instance of a MySQL service
1.  deploy the jar and bind the service to that application
1.  curl an endpoint that confirms MySQL functionality
1.  delete the app and service
1.  log out


The attached application comes from a build of the [Spring Music app] (https://github.com/ECSTeam/spring-music).  The jar has been copied here as to provide a stable deployable; if used in a concourse pipeline generating this jar as a part of the pipeline likely makes more sense.

The following environment variables are required to be set:

CF_API_URL:  the api endpoint of your foundation.

CF_USER_NAME:  the username of the account that will perform the `cf cs` and `cf push` commands.

CF_CREDENTIALS: the password for that user.

TARGET_ORG:  the org in which the service instance will be created and the app pushed.

TARGET_SPACE:  the space in which the service instance will be created and the app pushed.

CF_APPS_DOMAIN:  the apps domain. 

This script should be run after a MySQL tile upgrade to verify that the upgrade has no breaking changes to Java apps bound to MySQL Services.
