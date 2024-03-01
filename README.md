# ssl-certificat

certbot let's encrypted certificate 
https://vexxhost.com/resources/tutorials/secure-apache-letsencrypt-ubuntu20-04/

install certbot package on your ec2 instance by this command 

```
sudo snap install --classic certbot
```
Execute the following instruction on the command line on the machine to ensure that the certbot command can be run.
```
sudo ln -s /snap/bin/certbot /usr/bin/certbot
```



 after this run this command for create lets encrypted certificate 

 ```
 sudo certbot --apache
```

after this 
this will ask some question you so read this and give answer .

if you want to renew your certificate in three month so use this command 
```
0 0 1 */3 * sudo /usr/sbin/certbot-auto -q renew
```

The Certbot packages on your system come with a cron job or systemd timer that will renew your certificates automatically before they expire. You will not need to run Certbot again, unless you change your configuration. You can test automatic renewal for your certificates by running this command:

```
sudo certbot renew --dry-run
```

if you want to create ssl automatically 
```
sudo /usr/sbin/certbot-auto certonly --standalone --rsa-key-size 2048 --keep-until-expiring
```
