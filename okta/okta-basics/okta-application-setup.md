# Okta Application Setup

{% hint style="warning" %}
Currently only Labs Managers have admin access to Okta. If you have Okta issues, please reach out to your Engineering Manager.
{% endhint %}

An Okta Application defines a client application that can use the Okta domain for authentication.

The steps below are for setting up an application using the console... _hint hint_ these should all be available via the Okta API, maybe next step would be to write a small script... followed by automation?

## Setting up an SPA

{% hint style="info" %}
Access to the Labs Okta domain is restricted, work with your Engineering Manager for any issues.
{% endhint %}

1. Sign-in to the Labs Okta domain as an admin: [https://auth.lambdaschool.com](https://auth.lambdaschool.com)
2. [Create a new Single-Page App](https://dev-625244-admin.okta.com/dev/console/apps/new)
   * Name: The product name \(e.g. Bridgegood\)
   * Base URIs: The list of domains to whitelist for CORS \(Wildcards not allowed\)
     * http://localhost:3000/ \(For Create React Apps\)
     * https://bridgegood.dev
     * https://a.bridgegood.dev
     * https://b.bridgegood.dev
     * https://c.bridgegood.dev
     * https://d.bridgegood.dev
     * https://e.bridgegood.dev
     * https://f.bridgegood.dev
     * https://g.bridgegood.dev
   * Login redirect URIs: List of allowed redirect URIs after login \(Wildcards allowed\)
     * http://localhost:8080/implicit/callback
     * http://localhost:3000/implicit/callback
     * https://bridgegood.dev/implicit/callback
     * https://\*.bridgegood.dev/implicit/callback
   * Login redirect URIs: List of allowed redirect URIs after logout \(Wildcards allowed\)
     * http://localhost:8080
     * http://localhost:3000
     * https://bridgegood.dev
     * https://\*.bridgegood.dev
   * Group assignments
     * Everyone
     * Test Users
   * Grant type allowed
     * ✅ Authorization Code
     * ✅ Implicit
3. Save
4. Not done yet, we need to make a couple changes after we save...
5. Click 'Edit' on the general tab
   * Login initiated by: Either Okta or App
   * ✅ Display application icon to users
   * ✅ Display application icon in the Okta Mobile app
   * ✅ Redirect to app to initiate login
   * Initiate login URI: https://bridgegood.dev
6. For bonus points, click the ✎ on the application icon and add a nice icon for the app
7. Almost done!
8. Click 'Trusted Origins' under the 'API' menu
9. Click 'Add Origin' for each the root domain and each product subdomains:
   * Bridgegood Root: https://bridgegood.dev
   * Bridgegood a: https://a.bridgegood.dev
   * Bridgegood b: https://b.bridgegood.dev
   * Bridgegood c: https://c.bridgegood.dev
   * Bridgegood d: https://d.bridgegood.dev
   * Bridgegood e: https://e.bridgegood.dev
   * Bridgegood f: https://f.bridgegood.dev
   * Bridgegood g: https://g.bridgegood.dev
10. Done!

