# Azure DevOps (ADO)

### Add Git connection

To add <mark style="color:blue;">**Azure DevOps**</mark> personal git tokens in <mark style="color:purple;">**Brainboard,**</mark> you first need to generate an <mark style="color:blue;">**Azure DevOps**</mark> personal access token.

<details>

<summary>Steps to generate a <strong>personal access token</strong> on your <strong>Azure DO</strong> account.</summary>

1. Go to your [Azure DO page](https://dev.azure.com/).
2.  Click on the top-right icon and then select <mark style="color:blue;">**`Personal access tokens`**</mark>:

    <figure><img src="../../../.gitbook/assets/azure-devops-pat.png" alt=""><figcaption></figcaption></figure>
3.  It will open the **Personal Access Tokens** page. Click on <mark style="color:blue;">**`New token`**</mark> button.

    <figure><img src="../../../.gitbook/assets/azure-devops-add-pat.png" alt=""><figcaption></figcaption></figure>
4. In the modal, add the following information:
   * **Name** of the token.
   * You can set an **expiration date.**
   *   In the <mark style="color:blue;">**`code`**</mark> section, select <mark style="color:blue;">**`Full`**</mark><mark style="color:blue;">**&#x20;**</mark><mark style="color:blue;">**.**</mark>

       <figure><img src="../../../.gitbook/assets/azure-devops-pat-menu.png" alt=""><figcaption></figcaption></figure>
5.  Once the token is generated, you can copy it to add to <mark style="color:purple;">**Brainboard.**</mark>

    <figure><img src="../../../.gitbook/assets/azure-do-token-generated.png" alt=""><figcaption></figcaption></figure>

</details>

#### Steps to add the generated token in <mark style="color:purple;">**Brainboard**</mark>

1. Go to the [Git integration](https://app.brainboard.co/settings/integrations/git) settings page.
2. Click on <mark style="color:purple;">**`Integrations`**</mark><mark style="color:purple;">**&#x20;**</mark><mark style="color:purple;">**.**</mark>
3. In the section <mark style="color:purple;">**`Personal connections`**</mark> Click on <mark style="color:purple;">**`Add connection`**</mark>
4.  Select `Azure DevOps` tab<br>

    <figure><img src="../../../.gitbook/assets/CleanShot 2025-04-11 at 16.56.12@2x.png" alt=""><figcaption></figcaption></figure>
5. Add your credentials in the displayed window:
   * Name of the token. This is only for Brainboard, it will not be used when you do a pull request.
   * The URL of your Azure DevOps organization.
     *   To get this URL, the simplest way is to click on `Azure DevOps` on the top-left button then copy the URL of the browser

         <figure><img src="../../../.gitbook/assets/azure-do-orga-url.png" alt=""><figcaption></figcaption></figure>
   * Token: the token (secret) generated from your Azure DO account.
6. Then click on `Save and close` button.
7. Brainboard will verify if the credentials are valid:
   1.  If they are valid, Brainboard displays a success message and you can see the integration now in the Git connection page<br>

       <figure><img src="../../../.gitbook/assets/CleanShot 2025-04-11 at 17.07.55@2x.png" alt=""><figcaption></figcaption></figure>
   2.  If they are not, you'll receive an error about what is wrong. For example:<br>

       <figure><img src="../../../.gitbook/assets/CleanShot 2025-04-11 at 17.00.18@2x.png" alt=""><figcaption></figcaption></figure>

       <figure><img src="../../../.gitbook/assets/CleanShot 2025-04-11 at 17.03.42@2x.png" alt=""><figcaption></figcaption></figure>

### How to use

Please refer to the page [pull-requests.md](pull-requests.md "mention") to understand how you can use your git connections whether you want to do a pull request and import your code from Git.

### Edit or delete connection

1. Go to the [Git integration](https://app.brainboard.co/settings/integrations/git) settings page.
2. Click on `Integrations`
3. In the section `Personal connections` Click on the `Azure DevOps` integration that you want to edit or delete
4. Select the action you want to perform from the view

<figure><img src="../../../.gitbook/assets/CleanShot 2025-04-11 at 17.05.05@2x.png" alt=""><figcaption></figcaption></figure>
