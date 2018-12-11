# Bir 'Alexa Merhaba Dünya' Yeteneği Geliştirin
<img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/quiz-game/header._TTH_.png" />

[![Ses Arayüzü (SA)](https://user-images.githubusercontent.com/6242253/49790785-1f51f800-fd40-11e8-9f61-5adad636aa37.png)](./1-voice-user-interface.md)
[![Lambda Fonksiyonu](https://user-images.githubusercontent.com/6242253/49790804-2973f680-fd40-11e8-8932-fe79a3bff929.png)](./2-lambda-function.md)
[![SA'yı Koda Bağla](https://user-images.githubusercontent.com/6242253/49790840-3abd0300-fd40-11e8-9414-849bb162e09e.png)](./3-connect-vui-to-code.md)
[![Testler SEÇİLİ](https://user-images.githubusercontent.com/6242253/49797811-a2c81500-fd51-11e8-93d9-19182dff5570.png)](./4-testing.md)
[![Uyarlamalar](https://user-images.githubusercontent.com/6242253/49790859-43add480-fd40-11e8-87e5-2daea3d4f005.png)](./5-next-steps.md)

## Alexa Yeteneğinizi Test Edin

Bu aşamadan önce [bir Ses Arayüzü](./1-voice-user-interface.md) ve [bir Lambda fonksiyonu](./2-lambda-function.md) yarattık, sonra [bu ikisini birbirlerine bağladık](./3-connect-vui-to-code.md). Artık yeteneğinizin test aşamasına geçebiliriz.

1.  **[Amazon Alexa Geliştiricileri Ana Sayfası](https://developer.amazon.com/edw/home.html#/skills/list?&sc_category=Owned&sc_channel=RD&sc_campaign=Evangelism2018&sc_publisher=github&sc_content=Survey&sc_detail=hello-world-nodejs-V2_GUI-4&sc_funnel=Convert&sc_country=WW&sc_medium=Owned_RD_Evangelism2018_github_Survey_hello-world-nodejs-V2_GUI-4_Convert_WW_beginnersdevs&sc_segment=beginnersdevs)'nı tekrar ziyaret edin ve yeteneğinizi listeden seçin.** Not: Eğitime en başdan başladıysanız, ilgili sayfa halen tarayıcı sekmenizde açılı durumda olabilir.

2. Ekranın en üstündeki navigasyon menüsünde **Test** sekmesini tıklayarak **Alexa Simulator (Alexa Simülatörü)** uygulamasını açın.

3. **Test is disabled for this skill ("Bu yetenek için test devre dışı bırakılmıştır")** sürgüsüne tıklayın, sonra açılan menüde **Development ("Geliştirme")** seçeneğine tıklayarak simülatör uygulamasını etkinleştirin. Ekranda **Test is enabled for this skill ("Bu yetenek için test etkinleştirilmiştir")** ifadesi yer alacaktır.

4. Yeteneğinizin istediğiniz şekilde çalıştığını doğrulamak için **Alexa Simulator** uygulamasını kullanarak yeteneğinizi çağırın. 
**"Type or click and hold the mic"** ifadesinin bulunduğu metin kutusuna klavye ile giriş yapabilir ya da sesli giriş yapmak için Mic ("Mikrofon") butonunu tıklayıp basılı tutabilirsiniz.

	1. **Type** "Open" followed by the invocation name you gave your skill in [Step 1](./1-voice-user-interface.md). For example, "Open hello world".
	2. **Use your voice** by clicking and holding the mic on the side panel and saying "Open" followed by the invocation name you gave your skill.
	3. **If you've forgotten the invocation name** for your skill, revisit the **Build** panel on the top navigation menu and select **Invocation** from the sidebar to review it.

5. Ensure your skill works the way that you designed it to.
	* After you interact with the Alexa Simulator, you should see the Skill I/O **JSON Input** and **JSON Output** boxes get populated with JSON data. You can also view the **Device Log** to trace your steps.
	* If it's not working as expected, you can dig into the JSON to see exactly what Alexa is sending and receiving from the endpoint. If something is broken, AWS Lambda offers an additional testing tool to help you troubleshoot your skill.

6.  **Configure a test event in AWS Lambda.** Now that you are familiar with the **request** and **response** boxes in the Service Simulator, it's important for you to know that you can use your **requests** to directly test your Lambda function every time you update it.  To do this:
    1.  Enter an utterance in the service simulator, and copy the generated Lambda Request (JSON Input) for the next step.

    2.  **Open your Lambda function in AWS, open the Actions menu, and select "Configure test events."**![Configure Test events drop down](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/4-5-2-configure-test-event._TTH_.png)

    3.  **Select "Create new test event". Choose "Alexa Start Session" as the Event Template from the dropdown list.** You can choose any test event in the list, as they are just templated event requests, but using "Alexa Start Session" is an easy one to remember.  
![Alexa Start Session](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/4-5-3-alexa-start-session._TTH_.png)

    4.  Type in an Event Name into the **Event Name** field.  Delete the contents of the code editor, and paste the Lambda request you copied above into the code editor. The Event Name is only visible to you. Name your test event something descriptive and memorable. For our example, we entered an event name as "startSession". Additionally, by copying and pasting your Lambda Request from the service simulator, you can test different utterances and skill events beyond the pre-populated templates in Lambda.
<!-- out of date
![Copy request](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/fact/4-5-4-paste-request._TTH_.png)
-->
    5.  **Click the "Create" button.** This will save your test event and bring you back to the main configuration for your lambda function.

    6.  **Click the "Test" button to execute the "startSession" test event.**
![Test with event](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/4-5-5-save-and-test._TTH_.png)

        This gives you visibility into four things:

        *  **Your response, listed in the "Execution Result."**
![execution result](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/fact/4-5-5-1-execution-result._TTH_.png)

        *  **A Summary of the statistics for your request.** This includes things like duration, resources, and memory used.
![Summary](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/4-5-5-2-summary._TTH_.png)

        *  **Log output.**  By effectively using console.log() statements in your Lambda code, you can track what is happening inside your function, and help to figure out what is happening when something goes wrong.  You will find the log to be incredibly valuable as you move into more advanced skills.
![CloudWatch Logs](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/4-5-5-3-log-output._TTH_.png)

        *  **A link to your [CloudWatch](https://console.aws.amazon.com/cloudwatch/home?region=us-east-1#logs:) logs for this function.**  This will show you **all** of the responses and log statements from every user interaction.  This is very useful, especially when you are testing your skill from a device with your voice.  (It is the "[Click here](https://console.aws.amazon.com/cloudwatch/home?region=us-east-1#logs:)" link in the Log Output description.)

7.  **Other testing methods to consider:**

    *  [Echosim.io](https://echosim.io) - a browser-based Alexa skill testing tool that makes it easy to test your skills without carrying a physical device everywhere you go.
    *  [Unit Testing with Alexa](https://github.com/alexa/alexa-cookbook/tree/master/testing/postman/README.md) - a modern approach to unit testing your Alexa skills with [Postman](http://getpostman.com) and [Amazon API Gateway](http://aws.amazon.com/apigateway).

8.  **If your sample skill is working properly, you can now customize your skill.**

[![Next](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/buttons/button_next_customization._TTH_.png)](./5-next-steps.md)
