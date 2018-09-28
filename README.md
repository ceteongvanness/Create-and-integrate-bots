# Create and integrate bots
### Using Language Understanding in your bot
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



