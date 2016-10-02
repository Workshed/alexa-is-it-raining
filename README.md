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

1.6. Select 'alexa-skills-kit-color-expert' (this will create a template function for us to work from)

1.7. Configure the function as follows and then press "Next":

<img src="https://github.com/Workshed/alexa-is-it-raining/blob/master/images/functionConfig1.png" width="75%">
<img src="https://github.com/Workshed/alexa-is-it-raining/blob/master/images/functionConfig2.png" width="75%">

1.8. A summary of the configuration should be shown, if you're happy with it go ahead and press "Create function"

1.9. You now have a function! Although at the moment it just uses the sample code Amazon provide. To change this go to the "Code" tab, select all inside the box presented and replace it with the contents of "skill.js" from this repository.

<img src="https://github.com/Workshed/alexa-is-it-raining/blob/master/images/functionCode.png" width="75%">

1.10. Add in your own Dark Sky API key and your own latitude/longitude and then press "Save":

<img src="https://github.com/Workshed/alexa-is-it-raining/blob/master/images/changeDefaults.png" width="75%">

## 2. Create an Alexa Skill

2.1 Go to the Amazon Developer site https://developer.amazon.com/ and sign in

2.2 Select "Alexa" from the top navigation

<img src="https://github.com/Workshed/alexa-is-it-raining/blob/master/images/topNav.png" width="75%">

2.3 Select "Alexa Skills Kit"

<img src="https://github.com/Workshed/alexa-is-it-raining/blob/master/images/alexaSkillsKit.png" width="75%">

2.4 Press "Create a new Skill"

<img src="https://github.com/Workshed/alexa-is-it-raining/blob/master/images/createSkillButton.png" width="75%">

2.5. Configure the skill as follows (note that I've chosen to use the invocation "can i walk the dog" as it doesn't interfere with any built in Alexa/Echo functions):

<img src="https://github.com/Workshed/alexa-is-it-raining/blob/master/images/skillConfig1.png" width="75%">

2.6. Set the "Interaction Model" to the following (as this is a one shot skill it just requires the most basic interactions):

Intent Schema:

```
{
  "intents": [
    {
      "intent": "IsItRaining"
    }
  ]
}
```

Sample Utterances:

```
IsItRaining can I walk the dog
```

<img src="https://github.com/Workshed/alexa-is-it-raining/blob/master/images/skillConfig2.png" width="75%">

2.7. On the "Configuration" section add in the ARN of the Lambda function you created (you can find this at the top right of the Lambda page when editing the code of the function):

<img src="https://github.com/Workshed/alexa-is-it-raining/blob/master/images/skillConfig3.png" width="75%">

2.8. You are now able to test your new Alexa skill, go to the "Test" section and enter the utterance "can I walk the dog" and then press "Ask is it raining?". You should see the service respond successfully as shown:

<img src="https://github.com/Workshed/alexa-is-it-raining/blob/master/images/testSkill.png" width="75%">

If you have an Amazon Echo linked to the same account you used to create this skill it should already be set up for you to use!
