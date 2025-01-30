# Single sign-on (SSO)

{% hint style="info" %}
This feature is available only in the `Enterprise` plan and must be configured with the support team.
{% endhint %}

Brainboard offers SAML integrations to Enterprise accounts so that admins can easily manage users' access via their IDP

We support both `SAML 2` (recommended) & `OIDC`.

Brainboard's SAML integration allows you to connect Brainboard to your IDP so all users in your Brainboard organization can quickly and securely authenticate thought your IDP using SSO. New users will automatically be created in Brainboard when they sign in for the first time after been allowed in your IDP.



Once SSO is enabled for your organization, you will have your own tenant at Brainboard with a dedicated URL with the following format: `https://xxx.app.brainboard.co`

### Setup

#### 1. Tenant information

To get your tenant, you must reach out to the support team.

It might be shared by Brainboard team via email before the first onboarding session.

#### 2. Set up SAML in your IDP

We support SAML 2.0 standard.

Information needed to configure the SAML connectiong in your IDP:

| Identifier (Entity ID) | https://auth.brainboard.co/realms/{TENANT}                      |
| ---------------------- | --------------------------------------------------------------- |
| Reply/Assertion URL    | https://auth.brainboard.co/realms/{TENANT}/broker/saml/endpoint |
| Sign on URL            | https://{TENANT}.app.brainboard.co                              |

{% hint style="info" %}
Do not forget to replace `{TENANT}` with your tenant shared by the team.
{% endhint %}



Brainboard will configure automatically the following mappers (Azure Entra ID standard):

| User attribute | Attribute Name                                                       |
| -------------- | -------------------------------------------------------------------- |
| email          | `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress` |
| firstname      | `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/givenname`    |
| lastname       | `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/surname`      |
| groups         | (see below)                                                          |

#### 3. Automatic team provisioning and association from IDP Groups \[Optional]

Brainboard supports automatic teams provisioning and association.

Every time users log in, they will be assigned to their respective team using the IDP Groups. The team will be created if it doesn't exist yet.

The following instructions are for Azure Entra ID, but please reach out to our support team to configure your specific provider:

* In Azure Entra ID, open the `Enterprise Application` - `Single sign-on`
* Edit the `Attributes & Claims`
* Add a `Group claims` with the following configuration:
  * Groups assigned to the application
  * Source attribute: cloud-only group display names\
    (or any option to share a friendly name to Brainboard — this attribute will be used for Teams' names)

<figure><img src="../../.gitbook/assets/OVHtI7BllCiMMMgv.png" alt="" width="285"><figcaption><p>Azure Entra ID - Group claims</p></figcaption></figure>

#### 4. Share your IDP metadata

To finalize the configuration, you must share your IDP metadata (URL or XML file) to Brainboard support team.

The team will get back to you to confirm your new tenant URL and run a few tests if needed.



