# Alexa Is It Raining?
A simple Amazon Alexa Skill which calls the Dark Sky API to determine if it will rain in the next hour or not.

This README should also provide something of a guide to navigate the necessary parts of Amazons systems to get a basic Echo/Alexa skill up and running.

## Prequisites

* An Amazon account (you'll likely be prompted to agree to various AWS bits and pieces and may require a credit card - though it shouldn't cost you anything, the free plan should work fine)
* An API key for Dark Sky, available at https://darksky.net/dev/
* The latitude and longditude of the region you want to fetch the weather for

## 1. Create a Lambda function

1. Head over to https://console.aws.amazon.com/lambda/
2. Press the "Create a Lambda function" button:
![image](https://github.com/Workshed/alexa-is-it-raining/blob/master/images/image1.png "Create Lambda function")
3. You should be presented with something similar to the following:

4. Select "Node.js 4.3" for the runtime
5. Type "alexa" in the filter box
6. Select 'alexa-skills-kit-color-expert' (this will create a template function for us to work from).
