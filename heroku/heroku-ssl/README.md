# Heroku SSL

## HTTPS/SSL Support

Heroku does not offer https be default for free tier dynos with custom domains. One way around this is to utilize Cloudflare as a "proxy" between your domain's servers and your users.

This method relies on PointDNS to provide nameservers connected to the Heroku DNS target. Cloudflare exists as a abstraction layer in between PointDNS and the domain name.

### Objective

We will walk through the basic steps of setting up an account on Cloudflare and connecting it to your custom Heroku domain.

#### Requirements

* Lambda purchased custom domain
* PointDNS connected to target Heroku app
* cloudflare.com account

#### References

[What is SSL?](https://www.cloudflare.com/learning/ssl/what-is-ssl/)

[What is Cloudflare?](https://www.cloudflare.com/learning/what-is-cloudflare/)

### Getting Started

1. Create a free account on Cloudflare.com
2. Enter your site's custom domain name, then continue
3. Select the free plan, then continue

    !\[Cloudflare screen 1\]\(../assets/images/https-ssl-support/cloudflare-screen-01.png

   "Cloudflare screen 1"\)

4. Copy the two new name servers provided

    !\[Cloudflare nameservers screenshot\]\(../assets/images/https-ssl-support/cloudflare-screen-02.png

   "Cloudflare nameservers screenshot"\)

5. Send the new name servers to your SL with the template, below

!!! Example

```text
    Domain name: your-domain-name.com
    Cloudflare Name servers:
    1.
    2.
```

