# Plugins <small>- Installation & Configuration</small>

## Wordfence

!!! question "Wordfence"

    We are about to install Wordfence. This Wordpress plugin will allow your website to be protected from any hacking attempt that may occur. Your website will be secure, your data and your user's data as well.


<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/WN3fGueIBFM?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Install Wordfence on your server**

:    * Go to your Wordpress page.
:    * Click on *Plugins* in the left menu, then *Add New*.
:    * Type *Wordfence* in the search space at the top right. 
:    * Choose the *Wordfence Security - Firewall & Malware Scan* plugin, click on *Install*, then *Activate*.
:    * Click on *Settings* under *Wordfence Security - Firewall & Malware Scan*.
:    * A window appears, type your e-mail address. It will be used by Wordfence to send you reports and alerts about the security state of your website.
:    * Select the answer *No* and check the box about the terms and privacy. Click on {==*Continue*==}.
:    * Click on *No Thanks*.
:    * The *Wordfence* plugin is also in your left menu. Click on it and select *Dashboard*. 
:    * At the top of your page you can see two messages:
        * *`Do you want Wordfence to stay up-to-date automatically`*, click on {==*Yes, enable auto-update*==}.
        * *`To make your website as secure as possible, take a moment to optimize the WordfenceWeb Application Firewall`*, click on {==*Click here to configure*==}.

:    * On the new page, a window appears. Select ***Manual Configuration*** in the drop menu. Click on {==*Continue*==}.
:    * You can now see a sequence of characters, we are going to use a modified version of this to install Wordfence on your server. So ignore this sequence of characters, keep the window open and move on to the next step!

***

:    * Go back to your Lightsail instance and go to the *Homepage*. Click on the three little orange dots at the right of your instance insert.
:    * Click on *Connect*.
:    * Once you are inside your server's terminal, type or copy/paste directly the command below:
``` sh
sudo nano ../../etc/php-extra/DomainName.conf
```

:    * Don't forget to replace the *domainname* your yours. For example : edelstorm.conf . Then press <kbd>Enter</kbd>.
:    * With your keyboard's arrow, make the entry marker go under the text.
:    * Click on the small orange icon at the right bottom of the windows. Inside, paste the command you can find below:
``` sh
php_admin_value[auto_prepend_file] = '/home/runcloud/webapps/RuncloudApplicationName/wordfence-waf.php'
```

:    * Don't forget to replace the *RuncloudApplicationName* with your Runcloud application name. You can find it on your Runcloud page.
:    * Then click on the black part of the terminal. Do a right click to paste the command inside.
:    * Keep the <kbd>Ctrl</kbd> key pressed while pressing the <kbd>X</kbd> key.
:    * Then, press the <kbd>Y</kbd> key to validate your changes.
:    * Finally, press <kbd>Enter</kbd>.
:    * Close the terminal window and click on the 3 little dots at the right of your instance insert. Select *Reboot*. Confirm your action by clicking on the *Reboot* button.

!!! success "Wordfence is now installed on your server."

***

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/VK884Ah4qbk?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Wordfence settings**

:    * Go back on your Wordpress page. Click on {==*Close*==}.
:    * In the left Wordfence menu, click on *All options*.
:    * Scroll down and click on the {==*Import/Export Options*==} button.
:    * In the token field, paste the token below, then click on the {==*Import Wordfence Options*==} button:
``` sh
f1a72f34230a092898ba44e33687965f7c0e2a5ccb8421a1fde1da6d40ad912ab4fa2e305656d0e9fdd5dad999a7e7b366ab1ed45489be70f05a3daefa02bdeb
```

:    * Click on *Reload*. 
:    * In the left Wordfence menu, click on ***All options***.
:    * Scroll down to the *Firewall Options* part. Click on ***Basic Firewall Options***
:    * Click on the *Web Application Firewall Status* drop down menu and select ***Enabled and Protecting***.
:    * Click on {==Save changes==}.

!!! success "Wordfence is now set up."

***

!!! warning "**A COMPLETER**"

**Wordfence options**

:    * In the left menu, click on *Live Traffic*. You can find here a live vision of the users connected to your website.
:    * In the left menu, click on *Scan*. Click on the *Scan* button to scan your website and to check if everything is secured 
        * Scroll down a little bit and you will see the scan results. For the first one, click on the eye icon *Ignore* and select *Ignore until the files changes*. Repeat the same action for the other results but this time select *Always Ignore*.
:    * In the left menu, click on *Blocking*. Here you can create rules that will block some users from accessing your website.

***

## PageSpeed Ninja

!!! question "PageSpeed Ninja"

    We are about to install PageSpeed Ninja. This plugin accelerates the page loading on your website.


<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/D89StzJQuZ4?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**PageSpeed Ninja install**

:    * Click on *Plugins* in the left menu, then *Add New*.
:    * Type *PageSpeed Ninja* in the search space at the top right. 
:    * Choose the *PageSpeed Ninja* plugin, click on *Install*, then *Activate*.
:    * A message appears at the top of your page. Click on *Settings Page*.
:    * In the drop menu click on *Optimal*.
:    * Un-check *Send anonymous statistics*.
:    * Click on {==*Save*==}.
:    * On the new page, click on the ***Advanced*** tab.
:    * Scroll down to *Eliminate render-blocking Javascript and CSS in above-the-fold content*. Click on the ***green button*** to Cliquez sur le ***bouton vert*** pour deactivate this option.
:    * Do the same thing for the 2 next options, *Optimize images* and *Prioritize visible content*.
:    *  Scroll up the page and click on {==Save==}.

!!! success "PageSpeed Ninja is now installed."

***

<!-- ## Really simple SSL

!!! question "Really simple SSL"

    We are about to install Really simple SSL. This tools automatically detect your settings and configures your website to work in HTTPS (see <a href="/help/glossary/#https" target="_blank">Glossary</a>).


<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/QpQEaKtlTu8?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Really simple SSL install**

:    * Click on *Plugins* in the left menu, then *Add New*.
:    * Type *SSL* in the search space at the top right. 
:    * Choose the *Really simple SSL* plugin, click on *Install*, then *Activate*.
:    * An insert appears at the top of the page. Click on the {==*Go ahead, activate SSL!*==} blue button.

!!! success "Really simple SSL is now installed."

*** -->

## Redirection

!!! question "Redirection"

    We are about to install Redirection. Redirection will redirect the IP address (see the <a href="/help/glossary/#ipaddress" target="_blank">Glossary</a>) of your server to your secure domain name.


<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/mj39mDAv06o?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Redirection install**

:    * Click on *Plugins* in the left menu, then *Add New*.
:    * Type *Redirection* in the search space at the top right. 
:    * Choose the *Redirection* plugin, click on *Install*, then *Activate*.
:    * Click on *Settings* under *Redirection*.
:    * Scroll down the page and click on the {==*Start Setup*==} blue button.
:    * On the next page, check the 3 boxes, then click on the {==*Continue Setup*==} blue button.
:    * On the next page, every check mark goes green under *Checking your REST API*. If that's not the case, click on the {==*Retry*==} button.
:    * Click on the {==*Finish Setup*==} button.
:    * On the next page, click on the {==*Finished!*==} button.

***

:    * You are now on the *Options* page. Click on the *Redirects*. link the top of the page.
:    * Go on your Lightsail page and copy your instance's ***IP address***.
:    * In the *Add new redirection* section, write ***https://*** in the first field, then paste the ***IP address***.
:    * In the *Target URL* field, type the following address, but replace *YourDomainName.com* with your domain name :
``` sh
https://YourDomainName.com
```

:    * Click on the {==*Add Redirect*==} button.

:    * The fields are now empty. Paste your IP address in the first field.
:    * In the next field, type the following address, but replace *YourDomainName.com* with your domain name :
``` sh
https://YourDomainName.com
```

:    * Click on the {==*Add Redirect*==} button.

!!! success "Redirection is now installed."

***

## Smush image compression and optimization

!!! question "Smush image compression and optimization"

    We are about to install Smush. This plugin resizes, optimize, optimize and compress all of your images. Your website will be faster and lighter!


<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/tuDYbje8vKI?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>
***

**Smush Install**

:    * Click on *Plugins* in the left menu, then *Add New*.
:    * Type *Smush* in the search space at the top right. 
:    * Choose the *Smush image compression and optimization* plugin, click on *Install*, then *Activate*.
:    * Click on *Settings* under *Smush*.
:    * On the next page, click on the {==*Begin SETUP*==} blue button.
:    * Click on the right arrow, click again on the right arrow.
:    * Uncheck the *Allow usage data tracking* option.
:    * Click on the {==*Finish SETUP WIZARD*==} blue button.

!!! success "Smush is now installed."

***

## Redis Object Cache

!!! question "Redis"

    We are about to install Redis. This plugin will make your medias loading faster.


<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/5LLpovaEMTY?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Redis install**

:    * Click on *Plugins* in the left menu, then *Add New*.
:    * Type *Redis Object Cache* in the search space at the top right. 
:    * Choose the *Redis Object Cache* plugin, click on *Install*, then *Activate*.
:    * Click on *Settings* under *Smush*.
:    * Click on {==*Enable Object Cache*==}.

!!! success "Redis is now installed."

***

## Yoast SEO

!!! question "Yoast SEO"

    We are about to install Yoast SEO. This plugin will allow you to optimize your SEO. SEO is the process of maximizing the number of visitors to a particular website by ensuring that the site appears high on the search engine's list of results.


<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/C7PukHWqp8U?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Yoast SEO install**

:    * Click on *Plugins* in the left menu, then *Add New*.
:    * Type *Yoast SEO* in the search space at the top right. 
:    * Choose the *Yoast SEO* plugin, click on *Install*, then *Activate*.
:    * Click on *Settings* under *Yoast SEO*.
:    * In *First-time SEO configuration*, click on *Configuration wizard*.
:    * Cliquez on {==*Configure Yoast SEO*==}.
:    * Cliquez on {==*Next*==}.
:    * Select what type of website you are creating, then click on {==*Next*==}.
:    * Choose if your website will be introducing a company or an individual. Fill out the field depending on your answer then click on {==*Next*==}.
:    * Complete only if you want to or can then click on {==*Next*==}.
:    * On the next page, click on {==*Next*==} and again on {==*Next*==}.
:    * Click on {==*Get Google Authorization Code*==}.
:    * Log in or sign in to a Google account.
:    * Copy the code on the screen and paste it on the *Authorization Code* field on the Wordpress window.
:    * Click on {==*Authenticate*==}, click on {==*Next*==}, click again on {==*Next*==}, remove your e-mail address from the field and click on {==*Next*==}.
:    * Scroll down the page, click on {==*Next*==} and finally click on {==*Close*==}.

!!! success "Yoast SEO is set up."

***

## Google Analytics

!!! question "Google Analytics"

    We are about to install Google Analytics, so you can link your website to your Google Analytics account. You will have access to the data of your website, like how many users visited your website today, where they visited it from...


<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/ImS61sdT608?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Google Analytics install**

:    * Click on *Plugins* in the left menu, then *Add New*.
:    * Type *Google Analytics* in the search space at the top right. 
:    * Choose the *Google Analytics Dashboard for WP by ExactMetrics* plugin, click on *Install*, then *Activate*.
:    * Click on *Settings* under *Google Analytics Dashboard*.


***

**Google Analytics account creation**

:    * Go on <a href="https://analytics.google.com/analytics/web/" target="_blank">Google Analytics</a>
:    * If you already have an account, you can go to the next step. If not, stay with us!
:    * You will be asked to connect to your Google account. Type in your email and password.
:    * Once on the Google Analytics click on the {==*Register*==} button.
:    * You are now about to create an account for your website. You can go to the next step. You just created your Google Analytics account so the video will be slightly different from what you see on your screen. No worries although, you'll get to the same result!

***

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/2W-CXMYhHWc?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

:    * If you already had an account, go on *Administration*, then click on {==*Create an account*==}. For the others, you already are in the right form.
:    * Fill out the form. Add your website address with the *Https*.
:    * If you just created your account you can uncheck all the boxes at the end of the form, under the *Data sharing settings* section.
:    * Click on the {==*Get a tracking ID*==}.

:    * Go back on the Wordpress page and click on {==*Authorize plugin*==}.
:    * Click on the *Get access code* link, select your Google account and click on {==*Authorize*==}.
:    * A sequence of characters appears on the screen. Copy it.
:    * Go back on the Wordpress page and paste the code in the *Access code* field. Click on {==*Save Access Code*==}.
:    * Check that the settings are like the ones on the video, then click on {==*Save changes*==}.

!!! success "Google Analytics is now set up."

***

## Mailchimp

!!! question "Mailchimp"

    Mailchimp will allow your website to send emails. For example, you will be able to get notification from your website on your e-mail address, like answers to a contact form. You will also be able to send e-mails to your users (notification after an order, newsletter...).


<p><a href="/assets/images/wp/extentions/1.png" target="_blank"><img alt="mailchimp.com" src="/assets/images/wp/extentions/1.png"></a></p>

***

**Mailchimp account creation**

:    * Go on <a href="https://mailchimp.com/" target="_blank">Mailchimp.com</a>.
:    * Click on {==*Sign-Up Free*==}.
:    * fill out the sign-up form.
:    * Click on {==*Get Started!*==}.

!!! warning "Don't forget to confirm your email address. Mailchimp sent you an e-mail!"

!!! success "You now have a Mailchimp account."

***

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/l8dsBag30bk?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Link your Mailchimp account to your website**

:    * Click on *Plugins* in the left menu, then *Add New*.
:    * Type *MailChimp* in the search space at the top right. 
:    * Choose the *MailChimp for Wordpress* and *MailChimp UserSync*, plugins, click on *Install*, then *Activate*.
:    * Click on *Settings* under *MailChimp for Wordpress*.

:    * Now go on your Mailchimp account.
:    * In the top menu, at the right, click on the *name of your account* and on the drop menu click on *Profile*.
:    * Click on *Extras* and in the drop menu click on *API keys*.
:    * Scroll down the page to the *You don't have an API key* section. Click on the button {==*Create a key*==}.
:    * On the next page, you will find your new key. Copy it and go back to the Wordpress page.
:    * Paste the AP key in the *API key* field. Click on {==*Save*==}.

!!! success "Your Mailchimp account is now liked to your Wordpress website."

***

## 10 plugins to activate

??? note "What are those plugins for?""

    **WPS Hide Login**: To log in your Wordpress dashboard you generally have to add */wp-login* after your domain name. For security reasons, this plugin allows you to change the URL of the login form page. For example: https://edelstom.io/entrer.<br>

    **404 page - your smart custom 404 error page**: Create your custom 404 error page just like any other page using the WordPress Page Editor. Users will encounter this page if they try to connect to a non-existing page or one that does not exist anymore.<br>

    **Duplicate Page**: You will understand it later, but this plugin is very useful. It will allow you to duplicate pages or posts that you have created.<br>

    **Force Regenerate Thumbnails**: Takes care of the good quality of your photo display.<br>

    **Loco Translate**: Will allow you to translate your website. It is also useful with themes because sometimes some buttons or links stay in the language of the theme. With these tools, you will be able to translate those details in the language of your choice.<br>

    **SVG Support**: Help you to upload SVG files on your website. The SVG format is an XML-based vector image format for two-dimensional graphics with support for interactivity and animation.<br>

    **WP Retina 2x**: So your website is beautiful on every device, the plugin creates the image files, from your images, required by the High-DPI devices and it displays them to your visitors accordingly.<br>

    **Disable Gutenberg**: Let you use the classic Wordpress editor. *Gutenberg* is the new Wordpress editor, but this editor is not approved by the Wordpress community. <br>

    **Imsanity**:  Automatically resizes huge image uploads down to a size that is more reasonable for display in a browser, yet still more than large enough for typical website use.<br>

    **Easy Updates Manager**: Allows you to manage the Wordpress updates. You can, for example, prevent some automatic updates.

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/Z8gHm_MH1KM?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Install and activate**

:    * Click on *Plugins* in the left menu, then *Add New*.
:    * Copy paste the following plugins in the search space at the top right. <br>Then click on *Install*.
``` sh
404 page - your smart custom 404 error page
Disable Gutenberg
Duplicate Page
Easy Updates Manager
Force Regenerate Thumbnails
Imsanity
Loco Translate
SVG Support
WP Retina 2x
WPS Hide Login
```

:    * Once every plugin install, go on the left menu and click on *Installed Plugins*.
:    * Select all the plugins you just installed. Then go back at the top of the page and click on *Bulk actions*, then *Activate* and finally click on {==*Apply*==}.

!!! success "The 10 plugins are now installed and activated."

***

## 5 plugins not to activate

??? note "What are those plugins for?"

    **Crisp Live Chat**: This plugin will install a chat on your website. You will be able to speak directly with your users.<br>

    **Ultimate Member**: is a user profile et membership plugin. If needed, the plugin allows you to add user profiles to your site and help you to create advanced online communities and membership system.<br>

    **Disable Comments**: Will allow you to delete any possibility to post a comment on any post on your website.<br>

    **Cookie Notice**: Install a banner at the bottom of your website to let your users know that you use cookies on your website. This GDPR banner is now mandatory.

    **Super progressive web app**: This plugin combines the best of mobile web and the best of mobile apps to create a great mobile web experience. 

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/gDGP0jE49-4?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Install the plugins**

:    * Click on *Plugins* in the left menu, then *Add New*.
:    * Copy paste the following plugins in the search space at the top right. <br>Then click on *Install*.
``` sh
Cookie Notice (par dFactory)
Crisp Live Chat
Disable Comments
Ultimate Member
Super progressive web app
```

!!! success "Your 5 plugins are now installed!"

***
