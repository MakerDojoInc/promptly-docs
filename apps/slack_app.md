---
title: Slack App
description: Integrate Promptly app with Slack
layout: default
parent: Apps
nav_order: 3
---

# Slack App

Slack apps are similar to other apps on Promptly in that take in user input, call a series of LLMs and other processors, and return a rendered output in the provided template. These can be natively integrated into user's Slack workspace and can be called directly from Slack channels.

## Getting Started

To create a Promptly app that can be called from your Slack workspace, you need to first create a Slack app in your Slack workspace and use that configuration to create a Promptly app.

### Creating a Slack App

To create a Slack app, visit [https://api.slack.com/apps](https://api.slack.com/apps) and click the "Create New App" button. Pick "From scratch", you'll be prompted to give your app a name and select a workspace to install it in. Once you've done that, you'll be taken to the app configuration page.

Click on "OAuth & Permissions" under "Features" section in the sidebar and add the following scopes under "Bot Token Scopes" section:

![Slack OAuth Scopes](/assets/images/slack_bot_token_scopes.png)

Once added, click on "Install to Workspace" button under "OAuth Tokens for the workspace" section. You'll be prompted to authorize the app to be installed in your workspace. Click "Allow" to install the app in your workspace. Once done, you'll be taken back to the app configuration page where you can see "Bot User OAuth Token".

### Creating a Promptly App for Slack

Now go to "Apps" page on Promptly and click on the "Slack App" type to create a new app. You'll be prompted to give your app a name. Once you've done that, you'll be taken to the app editor. In the Slack App configuration, you'll need to add the following configuration:

![Slack App Configuration](/assets/images/slack_app_editor.png)

You can find this information in your Slack App's configuration page under "Basic Information" and "OAuth & Permissions" sections. Once you've added the configuration, click on "Save" button at the bottom of the page.

After the slack configuration is added, you can add processors to your app and configure them. Make sure to configure the "Application Output" based on the data from the processors. Once you're done, click on "Publish" button in the top right corner of the page. You'll be prompted to select the visibility level. Depending on the visibility level you publish the app with, it may be available to everyone or a select few users.

### Linking Promptly app with Slack

Once you've published your app, you'll need to link it with your Slack app. One the published Promptly App Editor page, click on the button "Integrate with Slack" at the bottom right corner. Copy the URL that gets shown in the dialog.

![Slack App Integration](/assets/images/slack_app_integration.png)

Now go to your Slack app's configuration page and click on "Event Subscriptions" under "Features" section in the sidebar. Turn on "Enable Events" and paste the URL you copied from Promptly app editor in the "Request URL" field.

![Slack App Event Subscriptions](/assets/images/slack_app_event_subscriptions.png)

After this, you'll need to subscribe to the following bot events under "Subscribe to Bot Events" section:

- `app_mention`

Click "Save Changes" to save the configuration. You'll be prompted to reinstall the app in your workspace. Click "Reinstall App" to reinstall the app in your workspace. You should now be able to add the app to your Slack channels and call it from there which will trigger the Promptly app and return the output.
