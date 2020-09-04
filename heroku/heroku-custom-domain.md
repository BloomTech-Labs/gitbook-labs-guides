# Heroku Networking

By default, Heroku creates an endpoint for your application like this: 

* `https://bridges-a-api.herokuapp.com/` 

This is okay, but if you want to use your custom product domain \(e.g. `a-api.bridgestoprosperity.dev`\) for your API, you can do this using Route 53.

1. In your Heroku application settings, click Add Domain
2. Your domain name will be a subdomain of your product domain, following the [naming standards](https://docs.labs.lambdaschool.com/standards/infrastructure/dns#dns-200-product-subdomains). For example, if your product domain is `bridgestoprosperity.dev` and your team letter is 'a', your API domain will be `a-api.bridgestoprosperity.dev`
3. Heroku will now issue you a specially generated domain to link traffic to your API subdomain
4. Open Route 53 in your AWS account
5. Open the hosted zone for your product
6. Click Create Record
7. Simple Routing
8. Define simple record
   * Record name: Your API domain \(e.g. `a-api)`
   * Route traffic to: IP address or another value
   * Value: The generated name from Heroku \(e.g. `concentric-turtle-7byvtq3pnb7n316b8zeu6peq.herokudns.com`\)
   * Record type: CNAME
9. Define simple record
10. Create records
11. Now you may need to wait a while for the internet DNS system to catch up
12. But once it does, you can now hit your Heroku app using `a-api.bridgestoprosperity.dev`
13. Done!



