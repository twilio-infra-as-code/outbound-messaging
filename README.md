# Setup  

1. [Install the Twilio CLI] (https://www.twilio.com/docs/twilio-cli/quickstart)
1. Install the Infra Plugin for the Twilio CLI 
```
$ twilio plugins:install plugin-twilio-infra
```
3. [Download and Install the Pulumi CLI](https://www.pulumi.com/docs/get-started/install/)
4. [Login in to the Pulumi service](https://www.pulumi.com/docs/reference/cli/pulumi_login/). You can either use the Pulumi service backend (you need to sign up to a free account for that) or the local storage, using one of the commands below:
```
# Pulumi Service backend
$ pulumi login

# Local storage
$ pulumi login --local
```
5. If you've never used the Twilio CLI with this project, create a new profile with 
```
$ twilio login
```
6. Log in to the project using
```
$ twilio profile:use <profile name>
```
7. Add the following environment variables: 

* `CHAT_SERVICE_SID`
* `FLEX_WORKSPACE_SID`
* `SMS_TASK_CHANNEL_SID` 
* `EVERYONE_TASK_QUEUE_SID`
* `TWILIO_PHONE_NUMBER`
* `FLEX_PROXY_SERVICE_SID`

8. If you don't have an environment defined, use the following command
```
$ twilio infra:environment:new <environment name>
```
9. Deploy the solution using: 
```
$ TWILIO_AUTH_TOKEN=xxxxxx twilio infra:deploy
```
10. In the Twilio [Console Settings page for Flex](https://www.twilio.com/console/flex/settings) make sure that the "Enable Dialpad" is Enabled

# Usage 
1. In Flex, click the Dialpad button (next to the microphone on the top right corner). At the bottom of the Dialpad, you will find the additional "Outbound SMS" text field. 
1. Enter the destination number and click "Start".
1. Clicking start generates a new [Task](https://www.twilio.com/docs/flex/admin-guide/core-concepts/routing#tasks). Click "Accept" to accept the incoming task and start a messaging conversation with the customer. 
