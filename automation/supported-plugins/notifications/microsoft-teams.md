# Microsoft Teams

This plugin allows you to send a notification to your MS Teams channel.

<figure><img src="../../../.gitbook/assets/CleanShot 2025-02-13 at 14.07.43@2x.png" alt=""><figcaption></figcaption></figure>

**Configuration options**

1. Task name: This name will be visible in the pipeline later when it is executed.
2. Title: title of the message that will be posted to the Teams channel.
3. Message: text to be sent.
4. Webhook URL of your MS Teams channel.
5. Hide pipeline URL: Do not add the button with link to the pipeline in the adaptive card of the message displayed in the Teams channel.
6. Ignore failure: if enabled, the execution of the following stage will be triggered even if the task fails.

#### Setup instructions

If you want to configure Microsoft Teams to receive notifications from Brainboard pipelines, an _incoming hook_ needs to be set up in the channel of your choice. To do so, follow the steps:

1.  Go to your Teams channel where you want the notification to be posted and open its configuration menu in the top-right corner and click on "Workflows":\


    <figure><img src="../../../.gitbook/assets/CleanShot 2025-02-13 at 14.56.13@2x.png" alt=""><figcaption></figcaption></figure>
2.  This will open the workflows configuration wizard. Search and select the line "Post to a channel when a webhook request is received":

    <figure><img src="../../../.gitbook/assets/CleanShot 2025-02-13 at 14.56.30@2x.png" alt=""><figcaption></figcaption></figure>
3.  Give it a name and click Next:\


    <figure><img src="../../../.gitbook/assets/CleanShot 2025-02-13 at 14.56.50@2x.png" alt=""><figcaption></figcaption></figure>


4.  Select the channel where you want the notification to be posted:\


    <figure><img src="../../../.gitbook/assets/CleanShot 2025-02-13 at 14.57.07@2x.png" alt=""><figcaption></figcaption></figure>
5.  Copy the generated webhook URL to use in Brainboard:\


    <figure><img src="../../../.gitbook/assets/CleanShot 2025-02-13 at 14.57.18@2x.png" alt=""><figcaption></figcaption></figure>

If you have an old configuration, follow the steps of this video:

{% embed url="https://www.youtube.com/watch?v=LOvWCNyXxLE" %}

{% hint style="warning" %}
&#x20;That configuration is deprecated by Azure and will be removed by the end of 2025.
{% endhint %}

