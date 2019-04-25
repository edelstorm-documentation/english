# Run Cloud <small>- AWS</small>

## Sign up

!!! info "Runcloud.io"

    Runcloud is a service that offers a secure and easy way to spread PHP apps. The goal of this step is to connect your Lightsail instance to the Runcloud.io interface so we can install and configure Wordpress on it.

<p><a href="../assets/images/aws/run-cloud/1.gif" target="_blank"><img alt="Runcloud.io" src="../assets/images/aws/run-cloud/1.gif"></a></p>

***

**Go to <a href="https://runcloud.io/" target="_blank">RunCloud.io</a>**

!!! info "AWS instance windows"
    Keep a window open on your Lightsail instance page. You will need to copy/paste your instance static IP address.

:    * Click on {==Sign Up==} at the top right.
:    * Fill the form and click on {==Create Free Account==}.

***

<p><a href="../assets/images/aws/run-cloud/2.gif" target="_blank"><img alt="Runcloud.io" src="../assets/images/aws/run-cloud/2.gif"></a></p>

***

:    * Confirm your account by clicking on {==Verify Registration==} in the email you just received.
:    * Connect to your account with your login and passwords by clicking on {==Sign in to Dashboard==}.

!!! success "You now have a Runcloud.io account!"

***

## Installation

***

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/s3hwb7DWV8E?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Install Runcloud on your Lightsail instance**

:    * Close the *Route 53* window.
:    * On the *Amazon Lightsail* page, click on ***Home***.
:    * Copy your server's IP address (the numbers you can find under your instance's name, in the grey rectangle).
:    * Go back on your ***Runcloud dashboard***.
:    * Click on ***Connect a New Server***.
:    * In the first field, name your server with your website name.
:    * Copy/paste the static IP of your instance in the second input.<br>
*You will find it on your Lightsail page, next to your instance name.*

:    * Then, put ***AWS*** as a Server Provider in the third field.
:    * Click on {==Connect this server==}.
:    * *RunCloud is going to generate an installation command on your server.* Copy it by clicking on the ***green icon*** on the right.
:    * Go back on Lightsail and connect to your SSH instance by clicking ***on the three dots*** next to your instance's name. Then click on ***Connect***.
:    * Once you are in the instance terminal, type the command below to obtain the admin rights, then press <kbd>Enter</kbd>.
``` sh
sudo su
```

:    * Click on the ***orange icon*** at the bottom right of the terminal and paste the installation command you just copied in the window.
:    * Click on the black part of the terminal, do a right click to paste the command inside, then press <kbd>Enter</kbd>.


!!! warning "Installation"

    The command is going to install Runcloud. **DO NOT LEAVE** the terminal before the process is done. It can take around 10 minutes.

***

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/XAsrWhi6wHo?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Save your MySQL<a href="/help/glossary/#mysql" target="_blank">&#185;</a> credentials**

:    *  Once the process is done, your ***database MySQL passwords*** will appear. Copy and paste it on a secure document on your computer! 

:    *  To copy on a terminal, you have to select what you want to copy, then click on the orange icon at the bottom right. You will find what you just select. You can now from this place, copy the content.

:    *  Open a text file so you can keep your MySQL access and save it in a secure place.<br>
*<a href="/help/glossary/#mysql" target="_blank">Click here</a> to know more about MySQL.*

!!! success "You now have access to the admin interface of your Runcloud.io instance!"

***

## Application's creation

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/9TLz0t-Ucfk?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Come back to Runcloud.io, you should now have access to your dashboard**

:    * On the left menu, click on {==Web Application==}.
:    * Click on {==Create Application==}.
:    * Fill out the form by starting with naming your application with your website's name.
:    * Add your domain name this way :
``` sh
*.VotreNomDeDomaine.com
```

:    * Add the domain name that you use for your instance.
:    * Choose the User by default *Runcloud*.
:    * Leave the by default *Public Path*.
:    * In the drop down menu, select the most recent PHP version.
:    * Select ***NGINX + Apache2 Hybrid (You will be able to use .htaccess)***.
:    * Choose the ***Production*** mode.
:    * Click on the *Advanced Settings* box.
:    * Scroll down the page to this field: *MAX_EXECUTION_TIME*. <br>
Write ***300*** in the field by replacing its content.

:    * Then go to the *MAX_EXECUTION_TIME* field.<br>
Write ***3000*** in the field by replacing its content.

:    * Click on {==Add Web Application==}.

!!! success "A space for an application is now available on your Lightsail instance."

***

## Configurations

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/BemZPIon4KQ?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Wordpress installation**

:    * On the left menu, click on {==Script Installer==}.
:    * In the drop down menu, select the ***Wordpress*** script.
:    * Click on {==Install==}.

***

**Domain name configuration**

:    * On the left menu, click on {==Domain Name==}.
:    * Add the domain name `www.example.com` to the field.
:    * Click on {==Attach Domain Name==}.
:    * Add the domain name `example.com` to the field.
:    * Click on {==Attach Domain Name==}.

!!! warning "The next step is only for the people that created a subdomain. If you did, it was when we configured your <a href="/instance-creation/#dns-zone" target="_blank">DNS zone</a>."
:    * Click on {==Attach Domain Name==}.
:    * Add your subdomain and domain name `SubDomain.example.com` to the field.
:    * Click on {==Attach Domain Name==}.

***

**Creation of the SSL security certificate**

:    * On the left menu, click on {==SSL/TLS==}.
:    * Scroll down the page, check the box ***Enable HSTS***.
:    * Select ***Let's Encrypt*** as an SSL method.
:    * Select ***Http-01***.
:    * Select ***Live*** as an environment.
:    * Click on {==Submit==}.
:    * Click on {==Create Let's Encrypt Request==}.

!!! success "Wordpress is now installed on your Lightsail instance. The domain name configuration is correct and the SSL security certificate is now activated."

***

## Database

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/iZXbEYeAHhM?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Database creation**

:    * Come back to the homepage by clicking on ***Back to web apps*** on the left.
:    * On the left menu, click on {==Database==}.
:    * Click on ***Create Database***.
:    * Name your database as you wish. Your website's name is a good option.
:    * Leave the field *Collation* empty by default.
:    * Click on {==Add Database==}.

!!! info "Information"

    Your app (Wordpress) needs a database to function. It will stock your website's and your user's information.

***

**Database admin user creation**

:    * Click on ***Create Database User***.
:    * In *Database User*, create your login, **save it in a file and store it in a secured place**.
:    * Generate a password and **copy it**! **Then, save it in a file and store it in a secured place**.
:    * Click on ***Add Database User***.

!!! info "Information"
    
    You need an admin account to access the Wordpress dashboard. This account will have all the rights on your website. Once the admin login/password created, you must keep it in a secure place/file.

<!-- ***

**Linking the admin account to your database**

:    * Click on ***Attach User***.
:    * Select the admin username in the drop-down list.
:    * Click on ***Attach User***.

!!! success "The database linked to an admin account is now available for Wordpress." -->

***

## Services install

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/ykHUQNlQRFg?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Let's activate services on Runcloud**

:    * Click on {==Services==} on the left menu.
:    * Scroll down and click on the ***setting icon*** next to the **Redis** logo.
:    * Click on ***Start***, then again on the {==Start==} button.
:    * Click on the ***setting icon*** next to the **Memcached** logo.
:    * Click on ***Start***, then again on the {==Start==} button.
:    * Click on the ***setting icon*** next to the **Beanstalkd** logo.
:    * Click on ***Start***, then again on the {==Start==} button.

!!! success "Redis is now active and set on your Runcloud account."

***

## SSH Key

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/vC_9UrVlE04?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Public SSH key setting for Runcloud.io**

:    * Click on {==SSH Key==} on the left menu.
:    * Click on {==Add SSH Key==}.
:    * Name your public SSH key in the *Label* field.
:    * Go to your `.ssh` file.
:    * Open `id_rsa.pub` with a text editor
:    * Copy the public key and paste it in the *Public Key* field of  Runcloud.io.
:    * Click on {==Add==}.

!!! success "Your SSH public key is now available. You will be able to connect remotely to your server through RunCloud.io."

***

## Wordpress configurations

:    * Click on ***Web application*** in the left menu.
:    * At the right, on the *Options* column, click on the {==Cog icon==}. 
:    * Select ***Set as default Web Application*** then click on {==Set As Default==}.

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/_E3wDzcMiis?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Wordpress database linking**

!!! info "Information" 
    You can now access your website! <br>Type your domain name `https://example.com` on the URL search bar of your browser. You will then have access to the Wordpress installation page.

:    * Select your language.
:    * Click on {==Continue==} then on {==Let's go!==} button.
:    * Inject your Runcloud.io database name (we defined it on the <a href="/run-cloud/#database" target="_blank">Database</a> step).
:    * Copy/paste your Runcloud.io ***administrator database name*** (we also did that on the <a href="/run-cloud/#database" target="_blank">Database</a> step).
:    * Copy/paste your Runcloud.io ***database password*** that you pasted in a file (again if you forgot, we did that during the <a href="/run-cloud/#database" target="_blank">Database</a> step).
:    * Leave the "by default" *Database Host* to `localhost`.
:    * Change your prefix's letters with something else than `wp_`, but keep the same format.
:    * Click on {==Submit==}.
:    * Click on {==Run the installation==}.

***

**Website and admin account configurations**

!!! info "Save your login!" 
    You are going to create admin access to your Wordpress website. **You must keep your login/password combination in a secure place!**

:    * Give your website a ***title***.
:    * Chose a ***login***, save it in a file and store it in a secured place.
:    * Generate a ***password***, copy and save it in a file and store it in a secured place.
:    * Add your admin ***e-mail*** address.
:    * Leave the *Search Engine Visibility* box unchecked.
:    * Click on {==Install Wordpress==}.
:    * You can now {==Log In==} to your Wordpress website.

!!! success "You now have access to your Wordpress interface."