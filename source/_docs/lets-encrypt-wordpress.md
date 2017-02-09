---
title: LetsEncrypt Certificates for WordPress
description: Create an SSL keypair with LetsEncrypt using a WordPress plugin.
tags: [golive]
categories: [golive]
---

This is a companion document to our guide [Enable Secure HTTPS Communication](/docs/enable-https/), for those wishing to use [Let's Encrypt](https://letsencrypt.org/). We'll cover the installation and use of the [WP Encrypt](https://wordpress.org/plugins/wp-encrypt/installation/) plugin to generate Let's Encrypt certificates.

<div class="alert alert-info">
<h3 class="info">Note</h3><p markdown="1">LetsEncrypt certificates will need to be regenerated and re-imported every 90 days. Consider alternate free solutions, like [Cloudflare](/docs/guides/cloudflare-enable-https/) before continuing.
</p>
</div>

## Install WP Encrypt

Install the [WP Encrypt](https://wordpress.org/plugins/wp-encrypt/installation/) plugin via SFTP or Git. To install via [Terminus](/docs/terminus), set the connection mode to [SFTP](https://pantheon.io/docs/sftp), then run: 

    terminus wp <site>.<env> -- plugin install wp-encrypt --activate

Once complete, the output will include at the end:

    Success: Installed 1 of 1 plugins.
     [notice] Command: <site>.dev -- 'wp plugin install wp-encrypt --activate' [Exit: 0]


## Generate Let's Encrypt Certificates

If you're only concerned with certificates for your live site, copy your changes to Test and then Live before continuing. Otherwise, repeat this section for each environment you want certificates for.

<div class="alert alert-info">
<h3 class="info">Note</h3><p markdown="1">If you have a custom domain name for your Dev or Test environment and want to generate certificates for that address, be sure to follow the steps below at that domain (not `<site>pantheonsite.io`).
</p>
</div>

1.  From the Wordpress Admin Dashboard, under Settings, click on **WP Encrypt**. You may also see an admin notice you can click on.

2.  Fill out the **Account Settings** section. This is how WordPress will identify you to the Let's Encrypt certificate authority:

    ![The WP Encrypt Settings page](/docs/assets/images/wp-encrypt-settings.png "WP-Encrypt Settings")

3.  Under **Additional Settings**, we recommend turning on **Expire Warnings Trigger**, to remind you when your certificates are about to expire.

4.  Once you've finished configuring WP Encrypt, click **Save Changes**. The page will now let you register an account with Let's Encrypt. Be sure to read the [Let’s Encrypt Subscriber Agreement](https://letsencrypt.org/documents/LE-SA-v1.1.1-August-1-2016.pdf) before clicking **Register Account**, which indicates your acceptance of the terms.

5.  Once you've registered, the **Generate Certificate** button appears. Once you click on it, WP Encrypt will generate your certificate and key files:

    ![The output of clicking on "Generate Certificate"](/docs/assets/images/wp-encrypt-output.png "WP-Encrypt Output")

## Export Let's Encrypt Certificates

1.  Using [SFTP](/docs/sftp/), copy these files to your local computer.

    <div class="alert alert-danger">
    <h3 class="info">Caution</h3><p markdown="1">
    These files define the encryption your site will use to establish secure communication. Do not copy them to a shared or otherwise unsecured computer, and consider removing them once you've completed this guide.
    </p>
    </div>

        sftp> get letsencrypt/live/<site>/*

2.  Copy the contents of `cert.pem`, `chain.pem`, and `private.pem` into the **HTTPS** tab of the Pantheon Site Dashboard, following the [Load Certificates into Pantheon](/docs/enable-https/#load-certificate-into-pantheon) section of the [Enable Secure HTTPS Communication](/docs/enable-https) guide.