# Using Language Understanding in your bot
#### Create a Language Understanding bot with Bot Service
1. In the Azure portal, select **Create new resource** in the menu blade and click **See all**.
![](https://github.com/ceteongvanness/Create-and-integrate-bots/blob/master/Image/AZR-A1.png)
2. In the search box, search for **Web App Bot**.
![](https://github.com/ceteongvanness/Create-and-integrate-bots/blob/master/Image/AZR-A2.png)
3. In the **Bot Service** blade, provide the required information, and click **Create**. This creates and deploys the bot service and LUIS app to Azure.
![](https://github.com/ceteongvanness/Create-and-integrate-bots/blob/master/Image/AZR-A3.png)
- Set **App name** to your bot's name. The name is used as the subdomain when your bot is deployed to the cloud (for example, etbotdemo.azurewebsites.net). This name is also used as the name of the LUIS app associated with your bot. Copy it to use later, to find the LUIS app associated with the the bot.
- Select the subscription, resource group, App service plan, and location.
- Select the **Language understanding (C#)** (SDK version: SDK v3)template for the **Bot template** field.
![](https://github.com/ceteongvanness/Create-and-integrate-bots/blob/master/Image/AZR-A4-1.png)
4. Confirm that the bot has been deployed by checking the Notifications will change from **Deployment in progress** to **Deployment succeeded**. Click ** Go to resource** button to open the bot's resources blade.
![](https://github.com/ceteongvanness/Create-and-integrate-bots/blob/master/Image/AZR-A5.png)
Once the bot is registered, click **Test in Web Chat** to open the Web Chat pane. Type "hello" in Web Chat.
![](https://github.com/ceteongvanness/Create-and-integrate-bots/blob/master/Image/AZR-A6.png)

The bot responds by saying "You have reached Greeting. You said: hello". This confirms that the bot has received your message and passed it to a default LUIS app that it created. This default LUIS app detected a Greeting intent.

### Modify the LUIS app
Log in to **https://www.luis.ai** using the same account you use log in to Azure. Click on **My apps**. in the list of apps, find the app that begins with the name specified in **App name** in the **Bot Service** blade when you created the Bot Service.
![](https://github.com/ceteongvanness/Create-and-integrate-bots/blob/master/Image/AZR-A7.png)

The LUIS app starts with 4 intents: Cancel, Greeting, Help, and None.
![](https://github.com/ceteongvanness/Create-and-integrate-bots/blob/master/Image/AZR-A8.png)

The following steps add the Note.Create, Note.ReadAloud, and Note.Delete intents:
1. Click on Prebuilt Domians in the lower left of the page. Find the Note domain and click Add domain.
![](https://github.com/ceteongvanness/Create-and-integrate-bots/blob/master/Image/AZR-A9.png)

2. We aren't going to use all of the intents included in the **Note** prebuilt domain. In the **Intents** page, click on each of the following intent names and then click the **Delete Intent** button.

- Note.ShowNext
- Note.DeleteNoteItem
- Note.Confirm
- Note.Clear
- Note.CheckOffItem
- Note.AddToNote
![](https://github.com/ceteongvanness/Create-and-integrate-bots/blob/master/Image/AZR-A10.png)
![](https://github.com/ceteongvanness/Create-and-integrate-bots/blob/master/Image/AZR-A11.png)

3. The only intents that should remain in the LUIS app are the following:
- Note.ReadAloud
- Note.Create
- None
- Help
- Greeting
- Cancel
![](https://github.com/ceteongvanness/Create-and-integrate-bots/blob/master/Image/AZR-A12.png)

4. Click the **Train** button in the upper right to train your app.
![](https://github.com/ceteongvanness/Create-and-integrate-bots/blob/master/Image/AZR-A13.png)

5. Click **PUBLISH** in the top navigation bar to open the **Publish** page.
![](https://github.com/ceteongvanness/Create-and-integrate-bots/blob/master/Image/AZR-A14.png)

	Click the **Publish to production slot**button.
![](https://github.com/ceteongvanness/Create-and-integrate-bots/blob/master/Image/AZR-A15.png)

	After successful publish, copy the URL displayed in the **Endpoint** column the **Publish App** page, in the row that starts with the Resource Name Starter_Key. Save this URL to use later in your bot's code. The URL has a format similar to this example:
https://westus.api.cognitive.microsoft.com/luis/v2.0/apps/3ad44df2-7789-4628-b09a-668c96699b1a?subscription-key=066a52d6483a419495da9277cebaea00&timezoneOffset=-360&q=


