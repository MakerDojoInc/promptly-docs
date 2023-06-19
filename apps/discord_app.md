---
title: Discord App
description: Integrate GPT powered Promptly app with Discord
layout: default
parent: Apps
nav_order: 4
---

# Discord App

Discord apps are similar to other apps on Promptly in that they take in user input, call a series of LLMs and other processors, and return a rendered output in the provided template. With a discord app an user can directly call the app from a discord channel and get the output in the channel. 


## Getting Started

To get started with creating a promtply discord app, you'll need to first create a discord bot and add that discord bot to the discord server you want to use the app in. 
Once you've done that, you can create a discord app on promptly and link it with the discord bot you created.

### Creating a Discord Bot

To create a Discord bot, visit [https://discord.com/developers/applications](https://discord.com/developers/applications) and click the "New Application" button. You'll be prompted to give your app a name. Once you've done that, you'll be taken to the app configuration page. Fill other fields like description and app icon as needed.


### Installing the Discord Bot

To add the Discord Bot to the server you can generate a URL by visiting the URL Generator section under OAuth2. When generating an installation URL make sure that you select the **bot** scope to ensure that the Discord bot has the required permissions to respond to slash commands. 

![Discord App OAuth2](/assets/images/discord_app_oauth_url_generator.png)

Make sure you select **Send Messages** & **Use Slash Commands** permission under **Bot Permissions** section.

Copy the generated URL, visit the URL in your browser and select the server you want to add the bot to. You'll be prompted to authorize the bot to be installed in your server. Click "Authorize" to install the bot in your server. Once done, you'll be taken back to the app configuration page where you can see the bot added to your server.

### Creating a Promptly App for Discord

Now go to "Apps" page on Promptly and click on the "Discord App" type to create a new app. You'll be prompted to give your app a name. Once you've done that, you'll be taken to the app editor. In the Discord App configuration, you'll need to add the following configuration:

![Discord App Configuration](/assets/images/discord_app_editor.png)

**Application ID** and **Public Key** can be found in your Discord App's configuration page under "General Information".
**Bot Token** can be found in your Discord App's configuration page under "Bot" section. 
>Note: Click on reset token before generating bot token for the first time.  

Promptly app is invoked from a discord channel via a [slash command](https://support.discord.com/hc/en-us/articles/1500000368501-Slash-Commands-FAQ#:~:text=Slash%20Commands%20are%20the%20new,command%20right%20the%20first%20time.). 
You can configure the **slash command name** and **slash command description** in the app configuration. Upon save Promptly will create a slash command in your discord app with the name and description you provided. The input options for your slash command will be the input fields you configure in the app editor.

After the discord configuration is added, you can add processors to your app and configure them. Make sure to configure the "Application Output" based on the data from the processors. 
Once you've added the configuration, click on "Save" button at the bottom of the page.
Upon Save, click on "Publish" button in the top right corner of the page. You'll be prompted to select the visibility level. 
>Note: Discord apps can only be published with **Public** visibility level.


### Linking Promptly app with Discord

Once you've published your app, you'll need to link it with your Discord app. One the Promptly App Editor page, click on the button "Integrate with Discord" at the bottom right corner. Copy the URL that gets shown in the dialog.

![Discord App Integration](/assets/images/discord_app_integration.png)

>Note: Integrate with Discord button will only be available when the Promptly App is published.

Now go to your discord app configuration page and click on "General Information". In the **INTERACTIONS ENDPOINT URL** field paste the URL you copied from Promptly app editor and hit Save.

![Discord App Interactions Endpoint](/assets/images/discord_app_webhook_config.png)