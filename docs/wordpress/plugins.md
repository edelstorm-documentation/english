# Plugins <small>- Installation & Configuration</small>

## Wordfence

!!! info "Wordfence"

    We are about to install Wordfence. This Wordpress plugin will allow your website to be protected from any hacking attempt that may occur. Your website will be secure, your data and your user's data as well.


<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/29I6-15PAi4?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Install Wordfence on your server**

:    * Go back to your Lightsail instance and go to the *Homepage*. Click on the three little dots at the right of your instance insert.
:    * Click on *Connexion*.
:    * Once you are inside your server's terminal, type directly the command below:
``` sh
sudo nano ../../etc/php-extra/domainname.conf
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

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/Ks4aKt5hWsU?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Wordfence settings**

:    * Go to your Wordpress page.
:    * Click on *Plugins* in the left menu, then *Add New*.
:    * Type *Wordfence* in the search space at the top right. 
:    * Choose the *Wordfence Security - Firewall & Malware Scan* plugin, click on *Install*, then *Activate*.
:    * You can now find *Wordfence* in your left menu, at the bottom. Click on it and select *Options*. 
:    * Scroll down and click on the *Import/Export Options* button.
:    * In the token field, paste the token below, then click on the *Import Wordfence Options* button:
``` sh
729374216505ce5b56b11477a07b46c9c9005eaa042749e28fd17e6d0cbf93f19fcafc4a88a0d0af3c18f7c116f108062cf3dcc918815031c6354f7c24c326c0
```

:    * Click on *Reload*. 

!!! success "Wordfence is now set up."

***

!!! warning "**A COMPLETER**"

**Wordfence options**

:    * In the left menu, click on *Live Traffic*. You can find here a live vision of the users connected to your website.
:    * In the left menu, click on *Scan*. Click on the *Scan* button to scan your website and to check if everything is secured.
:    * In the left menu, click on *Blocking*. Here you can create rules that will block some users from accessing your website.

***

## WP Fastest Cache

!!! info "WP Fastest Cache"

    We are about ot install WP Fastest Cache. A QUOI CA SERT.


<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/r3KcU8Vezic?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**WP Fastest Cache install**

:    * Click on *Plugins* in the left menu, then *Add New*.
:    * Type *Cache* in the search space at the top right.
:    * Choose the *WP Fastest Cache* plugin, click on *Install*, then *Activate*.
:    * You can now find *WP Fastest Cache* in your left menu at the bottom. Click on it.
:    * You are now going to check some options :
        * Check the *Cache System* box.
        * Check the *Preload* box, then the *Homepage*, *Posts*, *Categories*, *Pages*, *Tags*, *Attachments* and *Custom Post Types* boxes. Click on {==*Ok*==}.
        * Check the *New Post* box. Select *Clear all cache*, click on {==*Ok*==}.
        * Check the *Update Post*. Select  *Clear all cache*, click on {==*Ok*==}.
        * Check the *Minify HTML* box.
        * Check the *Minify CSS* box.
        * Check the *Gzip* box.
        * Check the *Disable Emojis* box.
        * Select your language.
:    * Click on the {==*Submit*==} button.

!!! success "WP Fastest Cache is now installed."

***

## Really simple SSL

!!! info "Really simple SSL"

    We are about to intall Really simple SSL. A QUOI CA SERT.


<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/ZzkqfX7SXU0?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Installation de Really simple SSL**

:    * Click on *Plugins* in the left menu, then *Add New*.
:    * Type *SSL* in the search space at the top right. 
:    * Choose the *Really simple SSL* plugin, click on *Install*, then *Activate*.
:    * An insert appears at the top of the page. Click on the {==*Go ahead, activate SSL!*==} blue button.

!!! success "Really simple SSL is now installed."

***

## Redirection

!!! info "Redirection"

    We are about to install Redirection. A QUOI CA SERT.


<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/b20_civFPxg?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

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

:    * Scroll down the page and check the *Force HTTPS* box.
:    * Click on the {==*Update*==} button.
:    * Scroll up to the top of the page and click on *Redirects*.
:    * In the *Add new redirection* section, write **https://* in the first field.
:    * Then go to your instance to copy your IP address. Paste it after the *https://*. Add an */* at the end
:    * In the next field, type the following address, but replace *YourDomainName.com* with your domain name :
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
:    * At the top of the page, click on *Clear Cache* then on : 
        * *Delete Cache* 
        * and *Delete Cache and Minified CSS/JS*


!!! success "Redirection is now installed."

***

## Velvet Blues Update URLs

!!! info "Velvet Blues Update URLs"

    We are about to install Velvet Blues Update URLs. If you move your WordPress website to a new domain name, you will find that internal links to pages and references to images are not updated. Instead, these links and references will point to your old domain name. This plugin fixes that problem by helping you change old urls and links in your website.


<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/D0Sg4K9h0lQ?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Velvet Blues Update URLs intall**

:    * Click on *Plugins* in the left menu, then *Add New*.
:    * Copy/paste the following name in the search space at the top right.
``` sh
Velvet Blues Update URLs
```

:    * Choose the *Redirection* plugin, click on *Velvet Blues Update URLs*, then *Activate*.
:    * Click on *Update URLs* under *Redirection*.
:    * Paste the following address on the first field *Old URL*. Replace *YourDomainName.com* with your domain name :  
``` sh
http://YourDomainName.com
```

:    * Paste the following address on the second field *New URL*. Replace *YourDomainName.com* with your domain name :  
``` sh
https://YourDomainName.com
```

:    * Check all the boxes on *Step 2*.
:    * Click on the {==*Update URL NOW*==} button.

!!! warning "Error message"

    This message *ERROR: Something may have gone wrong.* will appear. It is normal because you did not have actually any new URL to replace for now. When you will create new pages, the URLs will be replaced automaticlly.

!!! success "Velvet Blues Update URLs is now installed."

***

## Smush image compression and optimization

!!! info "Smush image compression and optimization"

    We are about to intall Smush. This plugin resize, optimize, optimise and compress all of your images. You website will be faster and lighter!


<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/H8CmaKUlSXs?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

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