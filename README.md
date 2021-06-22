# Outbound Messaging using Flex

Flex allows your agents to initiate conversations with your customers via any Twilio Messaging Channel, including SMS, WhatsApp, and Facebook Messenger.

Currently, outbound messages require additional development work presented in this repository based on this [official documentation](https://www.twilio.com/docs/flex/developer/messaging/outbound-messages-channels). Out-of-the-box, this example is showing how to initiate a SMS chat with a customer using the Twilio Flex interface. However, it is applicable to other messaging channels by changing the FlexFlow configuration. 

**Important Notice**: This repository is using Infra as Code (Pulumi and Twilio Provider) as described [here](https://www.twilio.com/blog/intro-to-infrastructure-as-code-with-twilio-part-1). If you are not familiar with this process, please read the documentation. Moreover, it is possible to use the code base to build your own implementation without Infra as Code. In order to do that, you can use the `src/resources` as the guide on how to configure the resources inside Twilio and the other directories inside `src/` should be the code you will be using (Twilio Functions, Flex Plugins etc).  


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

# Changelog

**0.0.1**: From this version on, this example is using the `twilio-pulumi-provider:^0.0.12` which uses the new Flex Plugin API. Therefore, the Flex Plugins on this repository where updated from the old version.

# Disclaimer

This software is to be considered "sample code", a Type B Deliverable, and is delivered "as-is" to the user. Twilio bears no responsibility to support the use or implementation of this software.