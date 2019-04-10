# Content Delivery Network <small>- AWS</small>

## Compartiment S3

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/-CmjJFF2gQQ?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

!!! info "S3"

    S3 est un service vous permettant d'héberger l'ensemble des médias de votre site internet, permettant ainsi à vos utilisateurs de les charger plus rapidement.

**Extension Offload**

:    * Dans le menu de gauche, cliquez sur ***Extensions***, puis ***Extensions installées***.
:    * Sélectionnez les deux extensions : *Akismet Anti-Spam *et *Hello Dolly*. 
:    * Supprimez-les les en sélectionnant l'action *Supprimer* dans le menu déroulant *Actions groupées*, oui sen cliquant sur {==Appliquer==}.
:    * Dans le menu de gauche, cliquez sur ***Ajouter***.
:    * Dans la barre de recherche, tapez ***Offload***.
:    * Choisissez *WP Offload media Lite for Amazon S3, DigitalOcean Spaces, and Google Cloud Storage* en cliquant sur le bouton {==Intaller==}.
:    * Attendez que l'intallation se finisse et cliquez sur {==Activer==}.
:    * Une fois sur la page *Extensions installées*, cliquez sur ***réglages*** sous WP Offload media Lite.


***

**Création d'un compartiment S3**

:    * Allez sur votre console de management AWS, cherchez le service *S3* dans la barre de recherche et cliquez dessus.
:    * Une fois sur l'interface S3, cliquez sur le bouton {==Créer un compartiment==}.
:    * Nommez votre compartiment et laisser la région par défaut : US East (N. Virginia).
:    * Cliquez sur {==Suivant==}.
:    * Laissez les options par défaut et cliquez sur {==Suivant==}.
:    * Décochez toutes les cases pour rendre public votre compartiment.
:    * Cliquez sur {==Suivant==}.
:    * Cliquez sur {==Créer un compartiment==}.

!!! success "Un compartiment de stockage S3 public est maintenant disponible. Il permettra de charger plus rapidement les différents médias de votre site Wordpress."

***

**Permissions du compartiment S3**

:    * Cliquez sur votre compartiment S3 et dans le menu de droite, cliquez sur {==Autorisations==}.
:    * Cliquez sur {==Statégies de compartiment==}.
:    * Dans l'éditeur, copiez / collez cette stratégie : 
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

:    * Remplacez ***YourBucketName*** par le nom que vous avez donné à votre compartiment.
:    * Une fois la stratégie éditée, cliquez sur {==Enregistrer==}.
:    * Cliquez sur le logo ***AWS***, en haut à gauche.

## Stratégie IAM

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/PIzAZV13pWI?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Création de la stratégie IAM**

:    * Cherchez le service IAM et cliquez dessus pour y accéder.
:    * Dans le menu de gauche, cliquez sur {==Stratégies==}.
:    * Cliquez sur {==Créer une stratégie==}.
:    * Cliquez sur l'onglet {==JSON==} pour accéder à l'éditeur en ligne.
:    * Une fois dans l'éditeur, supprimez le contenu existant et copiez / collez la stratégie IAM ci-dessous :
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

:    * Remplacez les deux ***YourBucketName*** par le nom que vous avez donné à votre compartiment.
:    * Cliquez sur {==Examiner une stratégie==}.
:    * Nommez la stratégie IAM.
:    * Cliquez sur {==Créer une stratégie==}.

!!! success "La stratégie IAM est prête à être utilisée pour votre futur utilisateur IAM."

***

## Utilisateur IAM

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/U219ST0LfBU?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Couplage de la stratégie IAM à votre utilisateur IAM**

:    * Dans le menu de gauche, cliquez sur {==Utilisateur==}.
:    * Cliquez sur {==Ajouter un utilisateur==}.
:    * Choisissez un nom pour votre utilisateur IAM.
:    * Cochez la case *Accès par programmation*.
:    * Cliquez sur {==Suivant : Autorisations==}.
:    * Cliquez sur *Attacher directement les stratégies existantes*.
:    * Dans la barre de recherche, tapez le nom de votre stratégie IAM.
:    * Sélectionnez votre stratégie IAM en cochant la case. 
:    * Dans la barre de recherche, tapez ***S3***.
:    * Sélectionnez la stratégie: *AmazonS3FullAccess* en cochant la case.
:    * Dans la barre de recherche, tapez ***Cloudfront***.
:    * Sélectionnez la stratégie: *CloudFrontFullAccess* en cochant la case.
:    * Enfin, dans la barre de recherche, tapez ***Admin***.
:    * Sélectionnez la stratégie: *AdministratorAccess* en cochant la case.
:    * Cliquez sur {==Suivant : Balises==}.
:    * Cliquez sur {==Suivant : Vérifications==}.
:    * Cliquez sur {==Créer un utilisateur==}.
:    * Cliquez sur {==Télécharger .csv==} pour conserver ces accès dans un fichier séparé.

!!! warning "Gardez cette fenêtre ouverte pour la prochaine étape et n'oubliez pas de stocker votre fichier .CSV contenant votre ID de clé d'accès et votre clé d'accès secrète dans un endroit sécurisé."

!!! success "Félicitation votre utilisateur IAM est lié à la bonne stratégie IAM et vous avez vos deux clés d'accès."

<!-- ***

## Injection des clés IAM

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/AFFWZ2afOAA?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Injection des clés d'accès IAM dans Wordpress**

:    * Aller sur la page d'accueil Runcloud.io
:    * Dans le menu de gauche, allez dans *Web Applications* et cliquez sur votre application Wordpress.
:    * Dans le menu de gauche, cliquez sur {==File Manager==}.
:    * Sélectionnez le fichier *wp-config.php* et cliquez dans le menu en haut sur *View/Edit*.
:    * Une fois dans l'éditeur, copiez / collez la commande ci-dessous à la suite de `define('WP_DEBUG', false);` : 
``` sh
define( 'AS3CF_SETTINGS', serialize( array(
    'provider' => 'aws',
    'access-key-id' => 'YourAccessKeyID',
    'secret-access-key' => 'YourAccessKeySecret',
) ) );
```

:    * Depuis votre interface IAM, remplacer *YourAccessKeyID* votre ID de clé d'accès et *YourAccessKeySecret* par votre clé secrète d'accès.

:    * Appuyez sur <kbd>Ctrl</kbd> + <kbd>S</kbd> pour sauvegarder les modifications. -->

***

## Certificat Manager

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/4ExrDofDvo4?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Création du certificat AWS**

:    * Revenez sur la console de management en cliquant sur le logo AWS en haut à gauche.
:    * En haut à droite, sélectionnez l'enplacement *US East (N. Virginia)*.
:    * Cherchez le service AWS *Certificate Manager* et cliquez dessus. 
:    * Dans la section de gauche *Allouer les certificats*, cliquez sur {==Démarrage==}.
:    * Cochez la case *Demander un certificat public* et cliquez sur {==Demander un certificat==}.
:    * Fournissez votre nom de domaine de cette façon : `*.exemple.com` et cliquez sur {==Suivant==}.
:    * Cochez la case *Validation DNS* et cliquez sur {==Vérification==}.
:    * Validez les informations fournient et cliquez sur {==Confirmer et demander==}.

***

**Validation DNS du nom de domaine fournit**

:    * Patientez un instant, AWS va générer une configuration DNS CNAME pour vous permettre de vérifier votre nom de domaine.
:    * Cliquez sur la petite flêche à gauche de votre nom de domaine.
:    * Copiez le début du nom CNAME. Copiez la suite de chiffres et lettres, arrêtez vous avant le point de votre nom de domaine.
:    * Rendez-vous dans votre interface Amazon Lightsail, cliquez sur {==Mise en réseau==} puis sur le nom de votre zone DNS.
:    * Cliquez sur {==Ajoutez un enregistrement==}.
:    * Sélectionnez *CNAME* comme type d'engistrement.
:    * Collez la suite de chiffres et lettres dans le *champ sous-domaine*.
:    * Retournez sur la page précédante *AWS certificate Manager* et copier la suite de chiffres et de lettres du champ *Valeur*.
:    * Retournez sur Amazon Lightsail et collez la suite dans le champ *Est résolu en*.
:    * Cliquez sur le ***bouton vert***.
:    *  Revenez sur *AWS Certicate Manager*, cliquez sur {==Continuer==} et patientez quelques minutes pendant la validation votre nom de domaine.
:    *  En rechargant la page, vous pourrez voir si votre nom de domaine a bien été validé. 

!!! success "Félicitations vous avez généré un certicat AWS pour votre nom de domaine."

***

## Cloudfront

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/D2qpY6Zg88U?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Création du Content Delivery Network**

:    * Revenez sur la console de management en cliquant sur le logo AWS en haut à gauche.
:    * Cherchez le service AWS *Cloudfront* et cliquez dessus.
:    * Cliquez sur {==Créer une distribution==}.
:    * Dans la section *Web*, cliquez sur {==Mise en route==}.
:    * Pour le *nom de domaine d'origine*, sélectionnez votre compartiment S3.
:    * Dans *Strategie de protocole d'utilisateur*, cochez la case ***Rediriger HTTP vers HTTPS***.
:    * Dans *Méthodes HTTP mises en cache*, cochez la case ***Personnaliser***.
:    * Dans *Compresser automatiquement les objets*, cochez la case ***Oui***.
:    * Dans *Autre nom de domaine (CNAME)*, tapez le sous-domaine `cdn.exemple.com`. Remplacez *exemple.com* pour votre nom de domaine.
:    * Cochez la case *Certificat SSL Personnalisé (exemple.com)*
:    * Cliquez sur le champ vide en dessous et sélectionnez le certificat SSL correspondant à votre nom de domaine.
:    * Enfin, dans le champ *Commentaire*, écrivez votre ***nom de domaine***. Pour savoir à quel nom de domaine correspond cette distribution 
:    * Cliquez sur {==Créer une distribution==}.

***

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/LcAJaWh4ccA?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Mapping CNAME Cloudfront et Amazon Lightsail**

:    * Cliquez sur l'ID de la distribution Cloudfront que vous venez de créer.
:    * Copiez le contenu de la section *Nom de domaine*.
:    * Revenez dans votre interface Lightsail, dans la section *Mise en réseau* puis dans la zone DNS de votre nom de domaine.
:    * Ajoutez un enregistrement, choisissez le type *CNAME*. Dans le champ *Sous domaine* tapez `cdn`, puis collez le contenu que vous venez de copier dans le second champ de droit. 
:    * Sauvegardez l'ensemble en cliquant sur le ***bouton vert***.

***

## WP Offload Media

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/aMhjGJkSvQ4?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Installation du plugin WP Offload Media**

:    * Allez sur votre interface d'administration Wordpress.
:    * Copiez l'***access keys in wp-config.phpp***.
:    * Rendez-vous sur votre interface Runcloud. Vous avez normalement toujours la page *Web application* ouverte.
:    * Cliquez sur le nom de votre application.
:    * Dans le menu de gauche, cliquez sur ***File Manager***.
:    * Sélectionnez ***wp-config.php*** dans la liste, puis remontez la page et cliquez sur ***View/Edit*** dans le menu bleu.
:    * Descendez l'éditeur jusqu'à trouver la ligne de code ***define( 'DB_COLLATE', '')***.
:    * Sautez une ligne et écrivez ceci:
``` sh
/** WP Offload */
```

:    * Allez à la ligne et collez la clé d'acces wp-config.php.
:    * Remplacez les étoiles de la ligne *access-key-id* par votre clé d'accès IAM (nous l'avons enregistré à la fin de <a href="/content-delivery-network-fr/#utilisateur-iam" target="_blank">cette étape</a>).
:    * Remplacez les étoiles de la ligne *secret-access-key* par votre clé secrète d'accès IAM (nous l'avons enregistré à la fin de <a href="/content-delivery-network-fr/#utilisateur-iam" target="_blank">cette étape</a>).
:    * Pour les utilisateur Mac, pressez les touches <kbd>cmd ou command</kbd> et <kbd>s</kbd>.
:    * Pour les utilisateur Windows, pressez les touches <kbd>ctrl</kbd> et <kbd>s</kbd>.

***

:    * Retournez sur la page Wordpress, descendez en bas de la page et cliquez sur {==Next==}.
:    * Dans le champ *Bucket*, tapez le nom de votre compartiment Amazon S3.
:    * Cliquez sur le bouton {==Save Bucket Setting ==}.
:    * Dans la section *URL REWRITING*, activez l'option *Custom Domain (CNAME)* et inscrivez `cdn.exemple.com`. Remplacer `exemple.com` par votre nom de domaine.
:    * Activez l'option *Force HTTPS*.
:    * Cliquez sur *Sauvegarder*.

!!! success "Félicitations, vous avez correctement configuré Amazon Cloudfront CDN pour votre site Wordpress."