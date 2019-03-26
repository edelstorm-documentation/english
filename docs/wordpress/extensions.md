# Extensions <small>- Installation & Configuration</small>

## Wordfence

!!! question "Wordfence"

    Nous sommes sur le point d'installer Wordfence. Il s'agit d'une extension de Wordpress permettant de protéger votre site d'éventuelles tentatives de piratage par exemple. Il permet de sécuriser votre site, vos données et celles de vos utilisateurs.

***

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/WN3fGueIBFM?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Installer de Wordfence sur votre serveur**
 
:    * Dans le menu de gauche, cliquez sur *Extensions*, puis sur *Ajouter une extension*.
:    * Dans la barre de recherche en haut à droite, tapez *Wordfence*. 
:    * Choisissez l'extension *Wordfence Security - Firewall & Malware Scan*, cliquez sur *Installer*, puis sur *Activer*.
:    * Une fenêtre apparaît, entrez votre adresse e-mail. Elle sera utilisée par Wordfence pour vous envoyer des comptes-rendus et alertes de sécurité de votre site.
:    * Sélectionnez la réponse *No* et cochez la case indiquant que vous acceptez les termes et la politique de protection des données de Wordfence. <br> Cliquez sur le bouton {==*Continue*==}.
:    * Cliquez sur *No Thanks*.
:    * L'extension *Wordfence* est présente dans votre menu de gauche en bas. Cliquez dessus et sélectionnez *Dashboard*. 
:    * Vous pouvez voir 2 messages en haut de votre page :
        * *`Do you want Wordfence to stay up-to-date automatically`*, cliquez sur {==*Yes, enable auto-update*==}.
        * *`To make your website as secure as possible, take a moment to optimize the WordfenceWeb Application Firewall`*, cliquez sur le bouton {==*Click here to configure*==}.

:    * Sur la nouvelle page une fenêtre apparait. Dans le menu déroulant sélectionnez ***Manuel Configuration***. Cliquez sur le bouton {==*Continue*==}.
:    * Une suite de caractère est disponible, nous allons utiliser une version modifiée de cette suite pour installer Wordfence sur votre serveur. Donc ignorez cette fenêtre, gardez-la ouverte et passez à l'étape suivante. 

***

:    * Rendez-vous sur votre instance Lightsail. Cliquez sur les trois petits points à coté du nom de votre instance et sélectionnez *Connect*.
:    * Une fois à l'intérieur du terminal de votre serveur, tapez directement la commande ci-dessous :
``` sh
sudo nano ../../etc/php-extra/nomdedomaine.conf
```

:    * N'oubliez pas de remplacer la partie *nomdedomaine* par le vôtre. Par exemple : edelstorm.conf . Puis appuyez sur <kbd>Entrer</kbd>.
:    * Avec la flèche de votre clavier, faire descendre le curseur de saisie sous le texte.
:    * Cliquez sur l'icône orange en bas à droite de la fenêtre du terminal et collez la commande suivante à l'intérieur.
``` sh
php_admin_value[auto_prepend_file] = '/home/runcloud/webapps/NomDeVotreApplicationRuncloud/wordfence-waf.php'
```

:    * N'oubliez pas de remplacer le *NomDeVotreApplicationRuncloud* par le nom que vous avez donné à votre application Runcloud. Vous pouvez le trouver sur votre page Runcloud.
:    * Cliquez ensuite sur la partie noire du terminal, faites un clic droit pour coller la commande à l'intérieur.
:    * Maintenez la touche <kbd>Ctrl</kbd> appuyée, tout en appuyant également sur la touche <kbd>X</kbd>.
:    * Puis, appuyez sur la touche <kbd>Y</kbd> pour valider vos changements.
:    * Enfin, appuyez sur la touche <kbd>Entrer</kbd>.
:    * Fermez la fenêtre de votre serveur et cliquez sur les trois petits boutons de votre instance. Sélectionnez {==*Redémarrer*==}. Confirmez l'action en cliquant sur le bouton {==*Redémarrer*==}.

!!! success "Wordfence est maintenant installé sur votre serveur."

***

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/VK884Ah4qbk?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Configuration de Wordfence**

:    * Revenez sur votre page Wordpress. Cliquez sur le bouton {==*Close*==}.
:    * Dans le menu de gauche, cliquez sur *All options*.
:    * Descendez en bas de la page et cliquez sur le bouton {==*Import/Export Options*==}.
:    * Dans le champ destiné à cet effet, collez le token suivant, puis cliquez sur le bouton {==*Import Wordfence Options*==} :
``` sh
28fcd2d531bca2da79409a53e36f26a7066b3be83f6f9938f6fdfa24a8b681e89af7bf1be829ee88905edb0d4173d99d1cac1ba448f15e0e6c683665a33e848e
```

:    * Cliquez sur {==*Reload*==}.   

!!! success "Wordfence est correctement configuré."

***

!!! warning "**A COMPLETER**"

**Les options de Wordfence** 

:    * Dans le menu de gauche, cliquez sur *Live Traffic*. Ici vous pouvez voir en live les utilisateurs se connectant à votre site.
:    * Dans le menu de gauche, cliquez sur *Scan*. Cliquez sur le bouton {==Scan==} pour vérifier la sécurité sur votre site. 
        * En descendant un peu sur la page, vous verrez les résultats du scan. Pour le premier résultat, vous pouvez cliquer sur l'oeil barré *Ignore* et sélectionnez *Ignore until the files changes*. Répétez l'opération en sélectionnant cette fois *Always Ignore* pour les autres.
:    * Dans le menu de gauche, cliquez sur *Blocking*. Ici vous pouvez créer des règles pour bloquer l'accès de votre site à certains utilisateurs.

***

## PageSpeed Ninja

!!! question "PageSpeed Ninja"

    Nous sommes sur le point d'installer PageSpeed Ninja. L'extension permet d'accélérer le chargement des pages de votre site.


<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/D89StzJQuZ4?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Installation de PageSpeed Ninja**

:    * Dans le menu de gauche, cliquez sur *Extensions*, puis sur *Ajouter une extension*.
:    * Dans la barre de recherche en haut à droite, tapez *PageSpeed Ninja*. 
:    * Choisissez l'extension *PageSpeed Ninja*, cliquez sur *Installer*, puis sur *Activer*.
:    * Un message apparait en haut de votre page, cliquez sur le lien *Page réglages*.
:    * Dans le menu déroulant, sélectionnez *Optimal*.
:    * Désélectionnez *Send anonymous statistics*.
:    * Cliquez sur le bouton {==*Save*==}.

!!! success "PageSpeed Ninja est correctement installé ."

***

## Really simple SSL

!!! question "Really simple SSL"

    Nous sommes sur le point d'installer Really simple SSL. Cet outil détecte automatiquement vos réglages et configure votre site web pour fonctionner en HTTPS (voir <a href="/aide/glossaire/#https" target="_blank">Glossaire</a>).


<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/QpQEaKtlTu8?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Installation de Really simple SSL**

:    * Dans le menu de gauche, cliquez sur *Extensions*, puis sur *Ajouter une extension*.
:    * Dans la barre de recherche en haut à droite, tapez *SSL*. 
:    * Choisissez l'extension *Really simple SSL*, cliquez sur *Installer*, puis sur *Activer*.
:    * Un encart apparaît en haut de votre page. Cliquez sur le bouton bleu {==*Activer SSL !*==}.

!!! success "Really simple SSL est correctement installé."

***

## Redirection

!!! question "Redirection"

    Nous sommes sur le point d'installer Redirection qui permet de rediriger l'adresse IP (voir <a href="/aide/glossaire/#adresseip" target="_blank">Glossaire</a>) de votre serveur vers votre nom de domaine sécurisé.


<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/mj39mDAv06o?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Installation de Redirection**

:    * Dans le menu de gauche, cliquez sur *Extensions*, puis sur *Ajouter une extension*.
:    * Dans la barre de recherche en haut à droite, tapez *Redirection*. 
:    * Choisissez l'extension *Redirection*, cliquez sur *Installer*, puis sur *Activer*.
:    * Cliquez sur *Réglages* sous *Redirection*.
:    * Descendez en bas de la page et cliquez sur le bouton bleu {==*Start Setup*==}.
:    * Sur la page suivante, cochez les 3 cases, puis cliquez sur le bouton bleu {==*Continue Setup*==}.
:    * Sur la page suivante, sous le titre *Checking yuor REST API* toutes les coches passent au vert. Si ce n'est pas le cas, cliquez sur le bouton {==*Retry*==}.
:    * Cliquez sur le bouton {==*Finish Setup*==}.
:    * Sur la page suivante, une fois la barre de progression chargée, cliquez sur le bouton {==*Finished!*==}.

***

:    * Vous êtes maintenant sur la page *Options*. En haut de la page, cliquez sur le lien *Redirects. 
:    * Dans la section *Add new redirection*, écrivez **https://* dans le premier champ.
:    * Puis rendez-vous sur votre instance pour copier votre adresse IP. Collez là à la suite de *https://*.
:    * À coté du bouton bleu *Add Redirect*, cliquez sur le petit rouage.
:    * Dans le deuxième menu déroulant de la section *When matched*, sélectionnez ***308 - Permanent Redirect***.
:    * Dans le champ *Target URL*, tapez l'adresse ci-dessous en remplaçant *VotreNomDeDomaine.com* par votre nom de domaine :
``` sh
https://VotreNomDeDomaine.com
```

:    * Cliquez sur le bouton {==*Add Redirect*==}.

:    * Les champs sont désormais vides, collez votre adresse IP dans le premier champ.
:    * Puis, dans le champ *Target URL*, tapez l'adresse ci-dessous en remplaçant *VotreNomDeDomaine.com* par votre nom de domaine :
``` sh
https://VotreNomDeDomaine.com
```

:    * Cliquez sur le bouton {==*Add Redirect*==}.

!!! success "Redirection est correctement installé."

***

## Smush compression d'image et optimisation

!!! question "Smush compression d'image et optimisation"

    Nous sommes sur le point d'installer Smush. Cette extension redimensionne, optimise et compresse toutes vos images. Votre site sera ainsi plus léger et rapide.


<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/tuDYbje8vKI?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Installation de Smush**

:    * Dans le menu de gauche, cliquez sur *Extensions*, puis sur *Ajouter une extension*.
:    * Dans la barre de recherche en haut à droite, tapez *Smush*. 
:    * Choisissez l'extension *Smush image compression and optimization*, cliquez sur *Installer*, puis sur *Activer*.
:    * Cliquez sur *Réglages* sous *Smush*.
:    * Sur la page suivante, cliquez sur le bouton bleu {==*Begin SETUP*==}.
:    * Cliquez sur la flèche de droite, cliquez à nouveau sur la flèche de droite.
:    * Décochez l'option *Allow usage data tracking*.
:    * Cliquez sur le bouton {==*Finish SETUP WIZARD*==}.

!!! success "Smush est correctement installé."

***

## Redis Object Cache

!!! question "Redis"

    Nous sommes sur le point d'installer Redis. L'extension permet d'accélérer le chargement des medias de votre site.


<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/5LLpovaEMTY?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Installation de Redis**

:    * Dans le menu de gauche, cliquez sur *Extensions*, puis sur *Ajouter une extension*.
:    * Dans la barre de recherche en haut à droite, tapez *Redis Object Cache*.
:    * Choisissez l'extension *Redis Object Cache*, cliquez sur *Installer*, puis sur *Activer*.
:    * Cliquez sur *Réglages* sous *Redis Object Cache*.
:    * Cliquez sur le bouton {==*Enable Object Cache*==}.

!!! success "Redis est correctement installé."

***

## Yoast SEO

!!! question "Yoast SEO"

    Nous sommes sur le point d'installer Yoast SEO. Cette extension vous aidera à optimiser le SEO de votre site. Le SEO ou référencement naturel peut être défini comme un ensemble de techniques visant à de positionner un site dans les premiers résultats naturels des moteurs de recherche.


<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/C7PukHWqp8U?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Installation de Yoast SEO**

:    * Dans le menu de gauche, cliquez sur *Extensions*, puis sur *Ajouter une extension*.
:    * Dans la barre de recherche en haut à droite, tapez *Yoast SEO*.
:    * Choisissez l'extension *Yoast SEO*, cliquez sur *Installer*, puis sur *Activer*.
:    * Cliquez sur *Réglages* sous *Yoast SEO*.
:    * Dans le 1er encart *First-time SEO configuration*, cliquez sur le lien *Configuration wizard*.
:    * Cliquez sur le bouton {==*Configure Yoast SEO*==}.
:    * Cliquez sur le bouton {==*Next*==}.
:    * Sélectionnez le type de site de votre site (blog, shop en ligne, portfolio...), puis cliquez sur {==*Next*==}.
:    * Choisissez si votre site représente une entreprise ou un particulier. Complétez le champ en fonction de votre réponse, puis cliquez sur {==*Next*==}.
:    * Il n'est pas nécessaire de fournir des liens si vous ne le voulez/pouvez pas, cliquez sur {==*Next*==}.
:    * Sur la page suivante, cliquez sur {==*Next*==} et à nouveau cliquez sur {==*Next*==}.
:    * Cliquez sur le bouton {==*Get Google Authorization Code*==}.
:    * Connectez-vous ou créez un compte Google.
:    * Copiez le code qui s'affiche à l'écran puis copiez-le dans le champ *Authorization Code* de la fenêtre Wordpress.
:    * Cliquez sur {==*Authenticate*==}, cliquez sur {==*Next*==}, cliquez à nouveau sur {==*Next*==}, retirez votre adresse e-mail du champ et cliquez sur {==*Next*==}.
:    * Descendez en bas de la page, cliquez sur {==*Next*==} et enfin cliquez sur {==*Close*==}.

!!! success "Yoast SEO est correctement configuré."

***

## Google Analytics

!!! question "Google Analytics"

    Nous sommes sur le point d'installer Google Analytics. Elle permet de lier votre site à Google Analytics. Vous aurez ainsi accès aux données générées par votre site, tel que le nombre de visiteurs par jour.


<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/ImS61sdT608?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Installation de Google Analytics**

:    * Dans le menu de gauche, cliquez sur *Extensions*, puis sur *Ajouter une extension*.
:    * Dans la barre de recherche en haut à droite, tapez *Google Analytics*.
:    * Choisissez l'extension *Google Analytics Dashboard for WP by ExactMetrics*, cliquez sur *Installer*, puis sur *Activer*.
:    * Cliquez sur *Réglages* sous *Google Analytics Dashboard*.

***

<p><a href="/assets/images/wp/extentions/2.png" target="_blank"><img alt="Runcloud.io" src="/assets/images/wp/extentions/2.png"></a></p>

***

**Création de compte Google Analytics**

:    * Rendez-vous sur <a href="https://analytics.google.com/analytics/web/" target="_blank">Google Analytics</a>
:    * Si vous avez déjà un compte, passez à l'étape suivante. Sinon, restez avec nous !
:    * Il vous sera demandé de vous connecter à votre compte Google. Entrez votre email et mot de passe.
:    * Une fois sur la page comme ci-dessus, cliquez sur {==*S'inscrire*==}.
:    * Vous allez maintenant créer un nouveau compte spécifique à votre site. Vous pouvez passer à l'étape suivante. Puisque vous venez de créer votre compte Google Analytics, la vidéo suivante sera légèrement différente de ce que vous verrez sur votre écran. Cependant pas d'inquiétude, vous arriverez au même résultat.

***

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/2W-CXMYhHWc?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

:    * Si vous aviez déjà créé un compte, rendez-vous sur *Administration*, puis cliquez sur {==*Créer un compte*==}. Pour les autres, vous êtes déjà sur le formulaire. 
:    * Remplissez le formulaire. Ajouter l'adresse de votre site en *Https*.
:    * Si vous venez de créer votre compte, vous pouvez décocher toutes les cases de la section *Paramètres de partage des données* à la fin du formulaire.
:    * Cliquez sur le bouton {==*Obtenir un ID de suivi*==}.

:    * Retournez sur la page Wordpress et cliquez sur le bouton {==*Autoriser le plugin*==}.
:    * Cliquez sur le lien *Obtenir un code d'accès*, sélectionnez votre compte Google puis cliquez sur le bouton {==*Autoriser*==}.
:    * Une suite de caractères s'affiche sur votre écran, copiez là.
:    * Retournez sur la page Wordpress et collez le code dans le champ *Code accès*. Cliquez sur le bouton {==*Sauvgarder le code d'accès*==}.
:    * Vérifiez que les réglages sont bien comme sur la vidéo puis cliquez sur {==*Sauvgarder les changements*==}.

!!! success "Google Analytics est correctement configuré."

***

## Mailchimp

!!! question "Mailchimp"

    Mailchimp est un système permettant à votre site d'envoyer des e-mails. Par exemple, vous pouvez ainsi recevoir sur votre adresse mail des notifications émanant de votre site, comme les formulaires de contacts remplis par vos utilisateurs par exemple. Vous pouvez aussi envoyer des e-mails à vos utilisateurs (notifications suite à une commande de produit, newsletter...)


<p><a href="/assets/images/wp/extentions/1.png" target="_blank"><img alt="mailchimp.com" src="/assets/images/wp/extentions/1.png"></a></p>

***

**Création d'un compte Mailchimp**

:    * Rendez-vous sur <a href="https://mailchimp.com/" target="_blank">Mailchimp.com</a>.
:    * Cliquez sur le bouton {==*Sign Up Free*==}.
:    * Complétez le formulaire avec votre adresse e-mail, un nom pour votre compte et un mot de passe.
:    * Cliquez sur le bouton {==*Get Started!*==}.

!!! warning "N'oubliez pas de confirmer votre adresse e-mail. Mailchimp vous a envoyé un mail."

!!! success "Vous avez créé un compte Mailchimp."

***

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/l8dsBag30bk?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Lier votre compte Mailchimp à votre site**

:    * Dans le menu de gauche, cliquez sur *Extensions*, puis sur *Ajouter une extension*.
:    * Dans la barre de recherche en haut à droite, tapez *MailChimp*.
:    * Choisissez les extensions *MailChimp* et *MailChimp UserSync*, cliquez sur *Installer*, puis sur *Activer*.
:    * Rendez-vous au niveau de l'extension *MailChimp for Wordpress* et cliquez en dessous sur *Réglages*. Vous vous retrouvez sur la page *General Settings* de l'extension.
:    * Rendez-vous maintenant sur votre compte MailChimp.
:    * Dans le menu du haut, à droite, cliquez sur le *nom de votre compte* et dans le menu déroulant cliquez sur *Profil*.
:    * Cliquez maintenant sur *Extras* et dans le menu déroulant cliquez sur *Clés API*.
:    * Descendez un peu la page au niveau du titre *Vous n'avez pas de clé API*. Cliquez sur le bouton {==*Créer une clé*==}.
:    * Sur la page suivante, vous trouverez votre nouvelle clé API. Copiez là et retournez sur votre page Wordpress.
:    * Collez votre clé API dans le champ *Clé API*. Cliquez sur le bouton {==*Sauvgarder*==}.

!!! success "Votre compte Mailchimp est désormais lié à votre site Wordpress."

***

## 10 extensions à activer

??? note "À quoi servent ces 10 extensions ?"

    **WPS Hide Login** : Généralement pour accéder à la page de connexion vous permettant d'accéder à un site Wordpress, il suffit d'ajouter */wp-login* après le nom de domaine de celui-ci. Pour des raisons de sécurité, cette application vous permet de choisir une autre terminologie pour accéder à la page de connexion à votre site. Par exemple : https://edelstom.io/entrer.<br>

    **404 page - your smart custom 404 error page** : Cette extension permet de personnaliser vos pages 404 error. Ces pages apparaissent quand un utilisateur essaye de se connecter à une page qu'il n'existe pas ou plus par exemple.<br>

    **Duplicate Page** : Vous le comprendrez plus tard, mais cette extension est très utile. Elle permet de dupliquer les pages ou articles que vous créez sur votre site.<br>

    **Force Regenerate Thumbnails** : Fait en sorte que l'affichage des photos sur votre site soit de bonne qualité.<br>

    **Loco Translate** : Vous permettra de traduire votre site. Il est également utile lors de l'utilisation de thèmes, parfois certains boutons ou liens restent dans la langue originale du thème. Cet outil permet de traduire ces détails-là dans la langue de votre choix.<br>

    **SVG Support** : Aide à l'upload de fichiers SVG sur votre site. Le format SVG est un langage XML utilisé pour décrire des graphiques en 2 dimensions. C'est à dire des images riches avec des caractéristiques telles que de la transparence, des effets de filtres et des animations.<br>

    **WP Retina 2x** : Pour que votre site soit beau sur tout support, cette extension créer des fichiers images au format retina haute résolution à partir de vos photos et les affiches à vos visiteurs utilisant des appareils haute définition (High-DPI).<br>

    **Disable Gutenberg** : Permet de continuer à utiliser l'éditeur classique de Wordpress. *Gutenberg* est un nouvel éditeur qui n'est pas validé par la communauté Wordpress. Nous le désactivons donc. <br>

    **Imsanity** : Redimnsionne les images trop importante uploadées sur le site.<br>

    **Easy Updates Manager** : Permet de manager les mises à jour Wordpress. Elle rend possible, par exemple, d'empêcher les mises à jours automatiques.

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/Z8gHm_MH1KM?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Installation et activation des 10 extensions**

:    * Dans le menu de gauche, cliquez sur *Extensions*, puis sur *Ajouter une extension*.
:    * Dans la barre de recherche, en haut à droite, copier-coller les noms des 10 extensions ci-dessous. <br>Une fois l'extension trouvée, cliquez sur *Installer*.
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

:    * Une fois toutes les extensions installées, rendez-vous dans le menu de gauche et cliquez sur *Extensions installées*.
:    * Sélectionnez toutes les extensions que vous venez d'installer. Retournez en haut de la page, cliquez sur *Actions groupées* puis sur *Activer* et enfin sur le bouton {==*Appliquer*==}.

!!! success "Vos 10 extensions sont correctement installées et activées."

***

## 5 extensions à ne pas activer tout de suite

??? note "À quoi servent ces 5 extensions ?"

    **Crisp Live Chat** : Vous permettra d'installer un chat sur voter site. Vous pourrez alors interagir en direct avec vos utilisateurs.<br>

    **Ultimate Member** : Si besoin, vous pourrez créer un système de profil et membership pour accéder à certaines parties de votre site ou certains services / produits.<br>

    **Disable Comments** : Vous permettra de potentiellement supprimer toute possibilité de laisser un commentaire sur les articles de votre site.<br>

    **Cookie Notice** : Génère une bannière en bas de la page d'accueil de votre site, indiquant à vos visiteurs que vous utilisez des cookies. Cette bannière est obligatoire d'après la régulation GDPR.

    **Super progressive web app** : Cette extensions associe le meilleur du Web mobile et le meilleur des applications mobiles pour créer une expérience Web mobile supérieure.

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/gDGP0jE49-4?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Installation des 5 extensions**

:    * Dans le menu de gauche, cliquez sur *Extensions*, puis sur *Ajouter une extension*.
:    * Dans la barre de recherche, en haut à droite, copier-coller les noms des 7 extensions ci-dessous. Nous vous avons indiqué pour certains l'auteur de l'extension pour que vous évitiez d'en sélectionner une autre similaire. <br>Une fois l'extension trouvée, cliquez sur *Installer*.
``` sh
Cookie Notice (par dFactory)
Crisp Live Chat
Disable Comments
Ultimate Member
Super progressive web app
```

!!! success "Vos 5 extensions sont correctement installées."

***
