 # Content Delivery Network <small>- AWS</small>

## S3 Bucket

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/VQztyuW6X24?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

!!! info "S3"

    S3 is a service that enables users to load your website’s media faster.

**S3 bucket creation**

:    * Go on your AWS management console, search for the service *S3* and click on it.
:    * Now that you are in the S3 interface, click on {==Create bucket==}.
:    * Name your bucket and leave the by default region: US East (N. Virginia).
:    * Click on {==Next==}.
:    * Leave the option by default and click on {==Next==}.
:    * Uncheck all the boxes so your bucket becomes public.
:    * Click on {==Next==}.
:    * Click on {==Create bucket==}.

!!! success "A storage S3 public bucket is now available! It will enable faster loading of your media on Wordpress."

***

**S3 bucket permissions**

:    * Click on your S3 bucket, then click on {==Permissions==} in the right menu.
:    * Click on {==Bucket Policy==}.
:    * Copy / paste the following policy on the editor : 
``` sh
{
 "Version": "2008-10-17",
 "Statement": [
 {
  "Sid": "AllowPublicRead",
  "Effect": "Allow",
  "Principal": {
   "AWS": "*"
  },
  "Action": "s3:GetObject",
  "Resource": "arn:aws:s3:::YourBucketName/*"
 }
 ]
}
```

:    * Don't forget to switch ***YourBucketName*** with the name you gave your bucket.
:    * Once the policy edited, click on {==Save==}.
:    * Click on the ***AWS*** logo at the top left of the page.

***

## IAM Policy

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/0hcbrfL1JCU?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**IAM policy initialization**
 
:    * Search for the IAM service and click on the result.
:    * In the left menu, click on {==Policies==}.
:    * Click on {==Create policy==}.
:    * To access the online editor, click on the {==JSON==} menu.
:    * Once in the editor, delete the existing content and copy / paste the IAM policy below:
``` sh
{
 "Version": "2012-10-17",
 "Statement": [
 {
  "Effect": "Allow",
  "Action": [
   "s3:CreateBucket",
   "s3:DeleteObject",
   "s3:Put*",
   "s3:Get*",
   "s3:List*"
  ],
  "Resource": [
   "arn:aws:s3:::YourBucketName",
   "arn:aws:s3:::YourBucketName/*"
  ]
 }
 ]
}
```

:    * Don't forget to replace two times *YourBucketName* by the name you chose for your bucket.
:    * Click on {==Review policy==}.
:    * Name the IAM policy.
:    * Click on {==Create policy==}.

!!! success "The IAM policy is now ready to be used for your future IAM user."

***

## IAM User

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/eC6ZIXPpCeI?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**IAM policy and IAM user linking**

:    * In the left menu, click on {==Users==}.
:    * Click on {==Add user==}.
:    * Choose a name for your IAM user.
:    * Check the *Programmatic access* box.
:    * Click on {==Next: Permissions==}.
:    * Click on *Attach existing policies*.
:    * Type your IAM policy's name in the search bar.
:    * Check the box to select your IAM policy
:    * Type ***S3*** in the search bar.
:    * Check the box to select this policy : *AmazonS3FullAccess*.
:    * Type ***Cloudfront*** in the search bar.
:    * Check the box to select this policy : *CloudFrontFullAccess*.
:    * Finally, type ***Admin*** in the search bar.
:    * Check the box to select this policy : *AdministratorAccess*.
:    * Click on {==Next: Tags==}.
:    * Click on {==Next: Review==}.
:    * Click on {==Create user==}.
:    * To keep your access in a separate file, click on {==Download .csv==}.

!!! warning "Keep this window open for the next step and don't forget to copy/paste and save your Access key ID and Secret access key in a secure place."

!!! success "Congratulations! Your IAM user is now liked to the right IAM policy and you have the two access keys."

<!-- 
***

## IAM key injection

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/_mJp7YdtVEk?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**IAM access key injection in Wordpress**

:    * Go to your Runcloud.io homepage
:    * On the left menu, click on *Web Applications* and click on your Wordpress application.
:    * Click on {==File Manager==} in the left menu.
:    * Select the *wp-config.php* file, then click on the {==View/Edit==} menu.
:    * Once in the editor, copy/paste the command below after `define('WP_DEBUG', false);` : 
``` sh
define( 'AS3CF_SETTINGS', serialize( array(
    'provider' => 'aws',
    'access-key-id' => 'YourAccessKeyID',
    'secret-access-key' => 'YourAccessKeySecret',
) ) );
```

:    * Then go to your IAM interface so you can replace *YourAccessKeyID* with your access key ID and *YourAccessKeySecret* with your secret access key.

:    * Type <kbd>Ctrl</kbd> + <kbd>S</kbd> to save your changes. -->

***

## Certificate Manager

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/PK7f-W6ZzCU?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**AWS Certificate creation**

:    * Go back to the Management Console by clicking on the AWS top left logo.
:    * On the top right corner, select *US East (N. Virginia)* location.
:    * Search for the AWS service *Certificate Manager* and click on it.
:    * In the left section *Provision certificates*, click on {==Get started==}.
:    * Check the *Request a public certificate* box and click on {==Request a certificate==}.
:    * Enter your domain name this way : `*.exemple.com` and click on {==Next==}.
:    * Check the *DNS validation* box and click on {==Review==}.
:    * Make sure the information on the screen are correct and click on {==Confirm and request==}.

***

**Domain name DNS validation**

:    * Wait for a moment, AWS is going to generate a DNS CNAME configuration. It will enable you to verify your domain name.
:    * Copy the beginning of the CNAME. Copy the serie of letters and numbers, stop just before your domain name's dot. 
:    * Go to your Amazon Lightsail interface. Click on {==Networking==} then on your DNS zone's name.
:    * Click on {==Add record==}.
:    * Select *CNAME* as a record type. Paste the beginning of the CNAME you copied on the *Subdomain* field. Then copy the *Value* you can find on the *AWS Certificate Manager* page and paste it in the *Maps to* field.
:    * Click on the ***green button*** to save.
:    * Go back to the *AWS Certificate Manager*, click on {==Continue==} and wait a few minutes while your domain name gets validated.
:    * Refresh your page to see if your domain name gets validated.

!!! success "Congratulations, you now have generated an AWS certificate for your domain name."

***

## Cloudfront

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/5atjyQXHVJw?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Content Delivery Network Creation**

:    * Go back to the homepage by clicking on the top left AWS logo.
:    * Search the AWS service *Cloudfront* and click on it.
:    * Click on {==Create distribution==}.
:    * In the *Web* section, click on {==Get started==}.
:    * For the *Origin domain name* filed, select your S3 bucket.
:    * In *Viewer Protocol Policy*, check the ***Redirect HTTP yo HTTPS*** box.
:    * In *Cached HTTP methods*, check the ***OPTIONS*** box.
:    * In *Compress Objects Automatically*, check the ***Yes*** box.
:    * In *Alternate domain name (CNAMEs)*, write this: `cdn.example.com`. Replace *example.com* with your domain name.
:    * Check the *Custom SSL Certificate (example.com)* box.
:    * In the next empty field, select the SSL certificate matching your domain name.
:    * Write your ***domain name*** in the *Comment* field, so you know for which domain name is this distribution. 
:    * Click on {==Create distribution==}.

***

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/j10DD5tqosw?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**CNAME Cloudfront and Amazon Lightsail Mapping**

:    * Click on the Cloudfront distribution ID.
:    * Copy *Domain name* content.
:    * Go back to the Lightsail interface, in the *Networking* section then in your domain name's DNS zone.
:    * Add a record and choose *CNAME record* on the first field. For the *subdomain* field type `cdn` and for the *Maps to* field paste the content you just copied. 
:    * Then save by clicking on the ***green button***.

***

## WP Offload Media

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/jbT2s1piWME?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**WP Offload Media plugin installation**

:    * Go to your Wordpress administration homepage.
:    * Copy the ***access keys in wp-config.php***.
:    * Go to the Runcloud page, you shloud be on the *Web application* page.
:    * click on your application's name.
:    * Click on ***File Manager*** in the left menu.
:    * Select ***wp-config.php*** on the list, then scroll up to click on ***View/Edit*** in the blue menu.
:    * Scroll the editor downuntil you find this line of code: ***define( 'DB_COLLATE', '')***.
:    * Skip a line and write this:
``` sh
/** WP Offload */
```

:    * Skip a line again and paste the wp-config.php access key.
:    *  Replace the stars next to *access-key-id* with your *IAM Access key ID* (we saved it at the end of <a href="/content-delivery-network/#iam-user" target="_blank">this step</a>).
:    * Replace the stars next to *secret-access-key* with your *IAM secret access key* (we saved it at the end of <a href="/content-delivery-network/#iam-user" target="_blank">this step</a>).
:    * For Mac users, press the keys <kbd>cmd</kbd> and <kbd>s</kbd>.
:    * For the Windows users, press the keys <kbd>ctrl</kbd> and <kbd>s</kbd>.

***

:    * Go back to the Wordpress page, scroll down and click on {==Next==}.
:    * Once there, put your S3 bucket name in the field and click on {==Save Bucket Setting==}.
:    * In the *URL REWRITING* tab, enable the *Custom Domain (CNAME)* option and put `cdn.example.com`. Replace `example.com` by your domain name.
:    * Enable *Force HTTPS* option.
:    * Click on *Save changes*.

!!! success "Congratulations, you have correctly set your CDN Amazon Cloudfront for your Wordpress website!"