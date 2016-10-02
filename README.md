# Alexa Is It Raining?
A simple Amazon Alexa Skill which calls the Dark Sky API to determine if it will rain in the next hour or not.

This README should also provide something of a guide to navigate the necessary parts of Amazons systems to get a basic Echo/Alexa skill up and running.

## Prequisites

* An Amazon account (you'll likely be prompted to agree to various AWS bits and pieces and may require a credit card - though it shouldn't cost you anything, the free plan should work fine)
* An API key for Dark Sky, available at https://darksky.net/dev/
* The latitude and longitude of the region you want to fetch the weather for

## 1. Create a Lambda function

1.1. Head over to https://console.aws.amazon.com/lambda/
1.2. Press the "Create a Lambda function" button:

<img src="https://github.com/Workshed/alexa-is-it-raining/blob/master/images/createLambda.png" width="50%">

1.3. You should be presented with something similar to the following:

<img src="https://github.com/Workshed/alexa-is-it-raining/blob/master/images/functionsRuntime.png" width="75%">

1.4. Select "Node.js 4.3" for the runtime
1.5. Type "alexa" in the filter box

<img src="https://github.com/Workshed/alexa-is-it-raining/blob/master/images/filteredFunctions.png" width="75%">

1.6. Select 'alexa-skills-kit-color-expert' (this will create a template function for us to work from).
1.7. Configure the function as follows and then press "Next":

<img src="https://github.com/Workshed/alexa-is-it-raining/blob/master/images/functionConfig1.png" width="75%">
<img src="https://github.com/Workshed/alexa-is-it-raining/blob/master/images/functionConfig2.png" width="75%">

1.8. A summary of the configuration should be shown, if you're happy with it go ahead and press "Create function"
1.9. You now have a function! Although at the moment it just uses the sample code Amazon provide. To change this go to the "Code" tab, select all inside the box presented and replace it with the contents of "skill.js" from this repository.

<img src="https://github.com/Workshed/alexa-is-it-raining/blob/master/images/functionCode.png" width="75%">

1.10. Add in your own Dark Sky API key and your own latitude/longitude:

<img src="https://github.com/Workshed/alexa-is-it-raining/blob/master/images/changeDefaults.png" width="75%">
