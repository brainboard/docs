# Bitbucket

### Add Git connection

To add a <mark style="color:blue;">**Bitbucket**</mark> personal app password in <mark style="color:$primary;">**Brainboard**</mark>, you first need to generate it in your <mark style="color:blue;">**Bitbucket**</mark> account.

<details>

<summary>Steps to generate an API token for your <strong>Bitbucket</strong> account.</summary>

1. Go to [API Token page in Atlassian Security center](https://id.atlassian.com/manage-profile/security/api-tokens)
2.  Create an API token with the following scopes:

    * Set the name and expiry date you want.
    * Select the <mark style="color:purple;">**Bitbucket**</mark> app.
    * Select the following scopes:
      * <mark style="color:blue;">**`write:pullrequest:bitbucket`**</mark>
      * <mark style="color:blue;">**`write:repository:bitbucket`**</mark>
      * <mark style="color:blue;">**`read:pullrequest:bitbucket`**</mark>
      * <mark style="color:blue;">**`read:repository:bitbucket`**</mark>

    <figure><img src="../../../.gitbook/assets/r9r8LPTCsB027FtH.png" alt="" width="375"><figcaption></figcaption></figure>
3. Once the token is generated, you can copy it to add to <mark style="color:$primary;">**Brainboard.**</mark>

</details>

#### Steps to add the generated token in Brainboard

1. Go to the [Git connections](https://app.brainboard.co/settings/integrations/git) page.
2. Click on <mark style="color:$primary;">**`Add connection`**</mark> .
3. Switch to the <mark style="color:$primary;">**`Bitbucket`**</mark> tab.

<figure><img src="../../../.gitbook/assets/bitbucket (1).png" alt=""><figcaption></figcaption></figure>

4. Add your credentials in the displayed window:

* **Name of the token.** This is only for <mark style="color:$primary;">**Brainboard**</mark>; it will not be used when you do a pull request.
* The **API URL** of your <mark style="color:blue;">**Bitbucket**</mark> server. By default, <mark style="color:$primary;">**Brainboard**</mark> uses <mark style="color:purple;">**`https://api.bitbucket.org/2.0`**</mark> , but you can set your own URL.
* **Email:** This is your **Atlassian/Bitbucket** email.
* **API token:** The API Token generated.

5. Then click on the <mark style="color:purple;">**`S`**</mark><mark style="color:$primary;">**`ave and close`**</mark> button.
6. <mark style="color:$primary;">**Brainboard**</mark> will verify if the credentials are valid.
   1.  **Valid credentials:** In this case, <mark style="color:$primary;">**Brainboard**</mark> displays a success message, and you can see the integration now in the **Git connections** page.<br>

       <figure><img src="../../../.gitbook/assets/CleanShot 2025-04-11 at 17.07.55@2x.png" alt=""><figcaption></figcaption></figure>
   2. **Invalid credentials:** In this case, you'll receive an error about what is wrong. For example, the one shared below.&#x20;

<figure><img src="../../../.gitbook/assets/bitbucket-error.png" alt=""><figcaption></figcaption></figure>

### How to use

Please refer to the page [pull-requests.md](pull-requests.md "mention") to understand how you can use your **Git connections** whether you want to perform a <mark style="color:blue;">**PULL**</mark> request and import your code from **Git.**

### Edit or delete connection

1. Go to the [Git connections](https://app.brainboard.co/settings/integrations/git) page.
2. Click on the connection that you want to delete.&#x20;
3. Click on the <mark style="color:red;">**`Delete Configuration`**</mark> button given at the bottom right corner of the page.
4. Click on the <mark style="color:red;">**`Delete`**</mark> button again to confirm your action.&#x20;

<figure><img src="../../../.gitbook/assets/delete-connec.png" alt=""><figcaption></figcaption></figure>
