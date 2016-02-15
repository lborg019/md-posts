# File uploader / External SMTP mailer system  #

This tutorial will teach you how to create a file upload system for your LAMP Stack server.
Since just uploading files might have no real world applicability, we will also attach each upload to an email and send it to whoever we want. We will delete the uploaded file afterwards since we will no longer need it.

This tutorial requires a LAMP Stack.

We will use:
- Bitnami's LAMP Stack (highly recommended, it should work on any LAMP Stack though)
- Pear (PHP extension)
- Your favorite text editor (Vim in my case)
- Gmail

Languages:
- HTML
- PHP

Assuming you already have a running LAMP Stack with your own `htdocs` folder,
you will need to create a `php/` folder (if you haven't already). Inside it, create an `upload.php` file and a `temp/` folder.

File Structure: `/opt/bitnami/apache2/htdocs`

```
----- htdocs/
---------- index.html
---------- css/
---------- js/
---------- php/
------------ upload.php
------------ temp/
```
`cs/` and `js/` are going to be irrelevant for this tutorial.
We will only be editing `index.html` and `upload.php`

Here's how your index.html might look like for testing purposes:

To install [pear](https://pear.php.net/), running the following:
`sudo /opt/bitnami/php/bin/pear install pear/Net_SMTP pear/Mail-1.2.0`</br>
If you are lucky enough to be using [Bitnami](https://bitnami.com/stack/lamp), you might get the following:
> Ignoring installed package pear/Net_SMTP</br>
Ignoring installed package pear/Mail</br>
Nothing to install

Meaning pear is already installed.

For this example we will be using a Gmail account.
Gmail is not inclined to let your application work. That is why we have to do adjust our Gmail account prior to use.

First, we go to this link:
Login to your Google Account, visit this link and turn Access for less secure apps 'ON'
https://www.google.com/settings/security/lesssecureapps

Then enable access to your Gmail account by clicking 'continue' on this link:
https://accounts.google.com/b/0/DisplayUnlockCaptcha

I'll leave this link for reference:
https://support.google.com/accounts/answer/6009563

{% highlight php %}
{% endhighlight php %}
