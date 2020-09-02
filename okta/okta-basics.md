# Okta Basics

{% hint style="warning" %}
Currently only APLs have direct access to Okta administration. If you have Okta issues, please reach out to your APL or Engineering Manager.
{% endhint %}

[Okta](https://www.okta.com/) is an identity management service that's used in Labs to provide centralized authentication for Labs applications.

We use a centralized identity management service because it is typically the way applications are authenticated in the industry. This gives our students practice using centralized identity management technologies like [OAuth](https://developer.okta.com/blog/2017/06/21/what-the-heck-is-oauth) and [OIDC](https://openid.net/connect/faq/).

We use Okta specifically because it is an [industry leader](https://www.okta.com/resources/access-management-leader-gartner-magic-quadrant) and has high-quality support and documentation.

## The Okta Account

Okta provides centralized identity management. This means that you can have a _single_ set of identities that can be used across many different applications. If you use Google services, you can see this in action as you log in to Google once but can move between Google apps \(Mail, Calendar, Sheets, etc.\) without having to log in each time.

We use Okta the same way. There is a _single_ Labs Okta account that has a set of identities that can access all Labs applications. These identities are test users that can be used by teams for testing their applications without having to constantly create new identities.

Since Labs applications are always under development, it's very handy to have a set of test identities readily available to test various aspects of your application.

Labs applications should _always_ authenticate using the alias \(auth.lambdalabs.dev\), though, for reference, the Labs Organization URL is: [https://dev-625244.okta.com](https://dev-625244.okta.comdashboard/)

### Logging In

As an APL, you'll have access to log in to the Labs Okta account to perform various tasks. Before Labs, you'll receive your login credentials and can use the following link to log in:

[Labs - Sign In](https://auth.lambdalabs.dev/)

If you can't login, please contact your engineering manager.

#### Test Users

A set of test users has been created that teams can use for authentication. These users follow a simple naming convention to make it easy for projects to authenticated.

There are 5 test users, each one using a 3-digit sequence for username and password:

| Username | Password | Mailbox |
| :--- | :--- | :--- |
| llama001@maildrop.cc | Test001Test | [https://maildrop.cc/inbox/llama001](https://maildrop.cc/inbox/llama001) |
| llama002@maildrop.cc | Test002Test | [https://maildrop.cc/inbox/llama002](https://maildrop.cc/inbox/llama002) |
| llama003@maildrop.cc | Test003Test | [https://maildrop.cc/inbox/llama003](https://maildrop.cc/inbox/llama003) |
| llama004@maildrop.cc | Test004Test | [https://maildrop.cc/inbox/llama004](https://maildrop.cc/inbox/llama004) |
| llama005@maildrop.cc | Test005Test | [https://maildrop.cc/inbox/llama005](https://maildrop.cc/inbox/llama005) |

Since the test users are using [maildrop.cc](https://maildrop.cc) for email, you can easily check their inbox if they are meant to receive email notifications from applications.

**Please take care** _**never**_ **to modify these users in any way!** These users are shared across Labs projects, so editing a user can affect other projects.

## Administrative Tasks

The following are administrative tasks that you'll need to perform in Okta to support Labs teams.

### Retrieve Product Client ID

There is a single Client ID for each product that must be supplied to Labs project teams in order for them to enable authentication. Each product will be set up as an Okta Application. The Client ID can be found using the Admin interface, by clicking on the Applications Tab.

Products have _one_ client id that is _shared_ among all active projects working on that product. Client IDs should _not_ be shared across products.

![](../.gitbook/assets/image%20%282%29.png)

### Issuer URI

The Issuer URI is also required for Labs projects to correctly configure authentication. For Labs projects, this value will _always_ be: [`https://auth.lambdalabs.dev/oauth2/default`](https://auth.lambdalabs.dev/oauth2/default)

### Add Project to Okta Application

Each Labs product has many projects in-flight at any given time. Each of these projects will need to have their production end-points configured in Okta for integration to work.

1. Navigate to the Applications list in the Admin interface
2. Click on the Okta Application you need to configure
3. Click on the 'General' tab
4. Click Edit
5. **Please do not change** _**any**_ **configuration other than described below.**
6. Ensure the project URIs have been added to the following attributes:
   1. Login Redirect URL: The AWS Amplify URL with `/implicit/callback` appended
   2. Logout Redirect URL: The AWS Amplify URL



