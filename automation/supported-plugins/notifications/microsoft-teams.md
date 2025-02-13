# Microsoft Teams

This plugin allows you to send a notification to your MS Teams channel.

<figure><img src="../../../.gitbook/assets/CleanShot 2025-02-13 at 14.07.43@2x.png" alt=""><figcaption></figcaption></figure>

**Configuration options**

1. Task name: This name will be visible in the pipeline later when it is executed.
2. Title: title of the message that will posted to the Teams channel.
3. Message: text to be sent.
4. Webhook URL of your MS Teams channel.
5. Hide pipeline URL: Do not add the button with link to the pipeline in the adaptive card of the message displayed in the Teams channel.
6. Ignore failure: if enabled, the execution of the following stage will be triggered even if the task fails.

#### Setup instructions

If you want to configure Microsoft Teams to receive notifications from Brainboard pipelines, an _incoming hook_ needs to be set up in the channel of your choice. To do so, follow the steps from the Brainboard video tutorial:

{% embed url="https://www.youtube.com/watch?v=LOvWCNyXxLE" %}

Here are the steps:

1.  Go to your Teams channel where you want the notification to be posted and open its configuration menu in the top-right corner and click on "Manage channel":

    <figure><img src="../../../.gitbook/assets/CleanShot 2025-02-13 at 14.25.45@2x.png" alt=""><figcaption></figcaption></figure>
2.  In the connector section, click on "Edit":

    <figure><img src="../../../.gitbook/assets/CleanShot 2025-02-13 at 14.28.12@2x.png" alt=""><figcaption></figcaption></figure>
3.  Click on "Configure" in the "Incoming Webhook" entry:

    <figure><img src="../../../.gitbook/assets/CleanShot 2025-02-13 at 14.28.22@2x.png" alt=""><figcaption></figcaption></figure>
4.  Add a name, logo of Brainboard and click on "Create" to generate a URL:

    <figure><img src="../../../.gitbook/assets/CleanShot 2025-02-13 at 14.38.54@2x.png" alt=""><figcaption></figcaption></figure>
5.  You copy the generated URL to use in the webhook in Brainboard:\


    <figure><img src="../../../.gitbook/assets/CleanShot 2025-02-13 at 14.39.47@2x.png" alt=""><figcaption></figcaption></figure>
