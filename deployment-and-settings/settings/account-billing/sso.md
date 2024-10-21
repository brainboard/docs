# Single sign-on (SSO)

{% hint style="info" %}
This feature is available only in the `Enterprise` version and must be configured with the support team.
{% endhint %}

### Single sign-on (SSO)&#x20;

Brainboard supports both `SAML 2` & `OIDC` that work with a wide range of login providers.

Brainboard support team will work with you to set up the SSO integration with your identity provider (IDP).



Once SSO has been enabled to your organization, you will have your own tenant at Brainboard with a dedicated URL with the following format: `https://xxx.app.brainboard.co`.



### Advanced settings

#### Automatic team provisioning and association from IDP Groups

Brainboard does support automatic teams provisioning and association. Every time a user login, they will be assigned to their respective team using the IDP Groups. The team will be created if it doesn't exist yet.

The following instructions are for Azure Entra ID but you are welcome to reach out to our support team to configure any other.

1. In Azure Entra ID, open the `Enterprise Application` - `Single sign-on`
2. Edit the `Attributes & Claims`
3. Add a `Group claims` with the following configuration:\
   \- Groups assigned to the application\
   \- Source attribute: cloud-only group display names

<figure><img src="../../../.gitbook/assets/OVHtI7BllCiMMMgv.png" alt=""><figcaption><p>Azure Entra ID - Group claims</p></figcaption></figure>

4. Then, reach out to the support team to enable it on your SSO if not the case.



