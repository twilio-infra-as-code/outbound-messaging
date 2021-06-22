# Outbound Messaging using Flex

Flex allows your agents to initiate conversations with your customers via any Twilio Messaging Channel, including SMS, WhatsApp, and Facebook Messenger.

Currently, outbound messages require additional development work presented in this repository based on this [official documentation](https://www.twilio.com/docs/flex/developer/messaging/outbound-messages-channels). Out-of-the-box, this example is showing how to initiate a SMS chat with a customer using the Twilio Flex interface. However, it is applicable to other messaging channels by changing the FlexFlow configuration. 

**Important Notice**: This repository is using Infra as Code (Pulumi and Twilio Provider) as described [here](https://www.twilio.com/blog/intro-to-infrastructure-as-code-with-twilio-part-1). If you are not familiar with this process, please read the documentation. Moreover, it is possible to use the code base to build your own implementation without Infra as Code. In order to do that, you can use the `src/resources` as the guide on how to configure the resources inside Twilio and the other directories inside `src/` should be the code you will be using (Twilio Functions, Flex Plugins etc).  

# Changelog

**0.0.1**: From this version on, this example is using the `twilio-pulumi-provider:^0.0.12` which uses the new Flex Plugin API. Therefore, the Flex Plugins on this repository where updated from the old version.

# Disclaimer

This software is to be considered "sample code", a Type B Deliverable, and is delivered "as-is" to the user. Twilio bears no responsibility to support the use or implementation of this software.