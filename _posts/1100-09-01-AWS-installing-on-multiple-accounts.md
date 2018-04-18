---
date: 2018-04-17
title: Multiple AWS Accounts
categories:
    - amazon web service
description: "A guide for installing Spinnaker on multiple AWS accounts from a single repo"
type: Document
---
Below we will explain how switching between environment profiles, gives the ability to switch between AWS account when you have a single Armory Spinnaker installation.

## What you will need

A file similar to */opt/spinnaker/env/prod.env* The name *prod* comes from the *stack* in a servergroup.

Example:
`armoryapinnaker-prod-v999`

## Setting Environment Variables And Secrets Specific to Environments

In the file */opt/spinnaker/env/prod.env*, many different environment variables can be set depending on the needs of that specific envrionment.  

If you want to customize the secrets for each environment, production, staging, development, you can add these to */opt/spinnaker/bin/secrets* with conditionals to obtain the correct credentials for the environment. You can see an example of conditional secrets in the secrets file at: [https://github.com/armory/spinnaker-config-deb/blob/master/deb-config/spinnaker/bin/secrets](https://github.com/armory/spinnaker-config-deb/blob/master/deb-config/spinnaker/bin/secrets)

## What Is Default.env

*/opt/spinnaker/env/default.env* is created by user-data in the *deploy-stage.* This can be edited, and most user defined env should be in 
*/opt/spinnaker/env/**{your-env-here}**.env*

## What Is Rendered.env

*/opt/spinnaker/env/resolved.env* file contains all the *env* in a combined to a single file.

## Additional Links

[Information on the Debian configuaration repository](https://github.com/armory/spinnaker-config-deb)

[More about env files](https://github.com/armory/spinnaker-config-deb/tree/master/deb-config/spinnaker/env)


