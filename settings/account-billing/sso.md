# Single sign-on (SSO)

{% hint style="info" %}
This feature is available only in the `Enterprise` plan and must be configured with the support team.
{% endhint %}

### Single sign-on (SSO)&#x20;

Brainboard supports both `SAML 2` & `OIDC` that work with a wide range of login providers.

Brainboard's support team will work with you to set up the SSO integration with your preferred identity provider (IDP).



Once SSO is enabled in your organization, you will have your own tenant at Brainboard with a dedicated URL with the following format: `https://xxx.app.brainboard.co`.

* `xxx` is a subdomain name that you provide. In most cases, it refers to your company name.

### Advanced settings

#### Automatic team provisioning and association from IDP Groups

Brainboard supports automatic teams provisioning and association.

Every time users log in, they will be assigned to their respective team using the IDP Groups. The team will be created if it doesn't exist yet.

The following instructions are for Azure Entra ID, but please reach out to our support team to configure your specific provider:

1. In Azure Entra ID, open the `Enterprise Application` - `Single sign-on`
2. Edit the `Attributes & Claims`
3. Add a `Group claims` with the following configuration:
   1. Groups assigned to the application
   2. Source attribute: cloud-only group display names

<figure><img src="../../.gitbook/assets/OVHtI7BllCiMMMgv.png" alt=""><figcaption><p>Azure Entra ID - Group claims</p></figcaption></figure>

4. Then, reach out to the support team to enable it on your SSO if not the case.



