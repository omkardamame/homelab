Before proceeding any further, make sure these settings are done properly. In URL, you can use your internal IP.

![[cf_settings_ssh 1.png]](https://github.com/omkardamame/homelab/blob/main/Cloudflare/cf_settings_ssh%201.png)

On your server, do change these settings as below,

![[cf_server1.png]](https://github.com/omkardamame/homelab/blob/main/Cloudflare/cf_server1.png)

Change your host to your desired hostname

![[cf_server2.png]](https://github.com/omkardamame/homelab/blob/main/Cloudflare/cf_server2.png)

Assuming you have logged in https://dash.cloudflare.com/, added your website and created a tunnel already.

![[cf_dashboard.png]](https://github.com/omkardamame/homelab/blob/main/Cloudflare/cf_dashboard.png)

Click on your website from 'Websites' from left pane.

Expand 'DNS' from left pane and go to records,

Click on 'Add record' button

![[cf_dns_records.png]](https://github.com/omkardamame/homelab/blob/main/Cloudflare/cf_dns_records.png)

Set 'Type' to 'CNAME' and in name as a alias, in my case I'm choosing 'ssh' and in 'target' copy the content of existing CNAME you have created while you were setting up a tunnel and click save

![[cf_ssh.png]](https://github.com/omkardamame/homelab/blob/main/Cloudflare/cf_ssh.png)

Now go back to Dashboard and go to Zero Trust > Access > Applications and click on 'Add an application'

![[cf_app.png]](https://github.com/omkardamame/homelab/blob/main/Cloudflare/cf_app.png)

Select self-hosted and enter an application name, subdomain and domain. You can change session duration if you want.

![[cf_app2.png]](https://github.com/omkardamame/homelab/blob/main/Cloudflare/cf_app2.png)

Use this settings,

![[cf_app3.png]](https://github.com/omkardamame/homelab/blob/main/Cloudflare/cf_app3.png)

Click next and enter 'Policy name' as 'allow-ssh'

![[cf_app4.png]](https://github.com/omkardamame/homelab/blob/main/Cloudflare/cf_app4.png)

In 'Configure rules' section, choose select which you like, like I did with 'Emails' which is allow login only for whitelisted emails only as shown below.

![[cf_app5.png]](https://github.com/omkardamame/homelab/blob/main/Cloudflare/cf_app5.png)

Click next and select browser rendering to SSH

![[cf_app6.png]](https://github.com/omkardamame/homelab/blob/main/Cloudflare/cf_app6.png)

Click on add application and now you can just go and visit your application through your specified link.

You will be asked for email login and verification code from your given email.
Then you'll have to enter user's name and password/private-key

![[cf_login.png]](https://github.com/omkardamame/homelab/blob/main/Cloudflare/cf_login.png)

References:
https://blog.cloudflare.com/browser-ssh-terminal-with-auditing/
https://youtu.be/xRlM71fCdbY?si=Cds4uWoQZ9Fcg5xG
https://youtu.be/ey4u7OUAF3c?si=hEVA5DjxuAEbgUKn
