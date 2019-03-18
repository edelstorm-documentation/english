# Extensions <small>- Installation & Configuration</small>

## Wordfence

!!! info "Wordfence"

    Nous sommes sur le point d'installer Wordfence. Il s'agit d'une extension de Wordpress permettant de protéger votre site d'éventuelles tentatives de piratage par exemple. Il permet de sécuriser votre site, vos données et celles de vos utilisateurs.


<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/29I6-15PAi4?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Installation de Wordfence sur votre serveur**

:    * Retournez sur votre instance Lightsail et rendez-vous sur votre *Accueil*. Cliquez sur les trois petits boutons de votre instance. 
:    * Cliquez sur *Connexion*.
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

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/Ks4aKt5hWsU?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Configurer Wordfence**

:    * Rendez-vous sur votre page Wordpress.
:    * Dans le menu de gauche, cliquez sur *Extensions*, puis sur *Ajouter une extension*.
:    * Dans la barre de recherche en haut à droite, tapez *Wordfence*. 
:    * Choisissez l'extension *Wordfence Security - Firewall & Malware Scan*, cliquez sur *Installer*, puis sur *Activer*.
:    * L'extension *Wordfence* est maintenant présente dans votre menu de gauche en bas. Cliquez dessus et sélectionnez *Options*. 
:    * Descendez en bas de la page et cliquez sur le bouton {==*Import/Export Options*==}.
:    * Dans le champ destiné à cet effet, collez le token suivant, puis cliquez sur le bouton {==*Import Wordfence Options*==} :
``` sh
729374216505ce5b56b11477a07b46c9c9005eaa042749e28fd17e6d0cbf93f19fcafc4a88a0d0af3c18f7c116f108062cf3dcc918815031c6354f7c24c326c0
```

:    * Cliquez sur {==*Reload*==}. 

!!! success "Wordfence est correctement configuré."

***

!!! warning "**A COMPLETER**"

**Les options de Wordfence** 

:    * Dans le menu de gauche, cliquez sur *Live Traffic*. Ici vous pouvez voir en live les utilisateurs se connectant à votre site.
:    * Dans le menu de gauche, cliquez sur *Scan*. Cliquez sur le bouton {==Scan==} pour vérifier la sécurité sur votre site.
:    * Dans le menu de gauche, cliquez sur *Blocking*. Ici vous pouvez créer des règles pour bloquer l'accès de votre site à certains utilisateurs.

***

## WP Fastest Cache

!!! info "WP Fastest Cache"

    Nous sommes sur le point d'installer WP Fastest Cache. L'extension permet d'accélérer le chargement des pages de votre site.


<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/r3KcU8Vezic?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Installation de WP Fastest Cache**

:    * Dans le menu de gauche, cliquez sur *Extensions*, puis sur *Ajouter une extension*.
:    * Dans la barre de recherche en haut à droite, tapez *Cache*. 
:    * Choisissez l'extension *WP Fastest Cache*, cliquez sur *Installer*, puis sur *Activer*.
:    * L'extension *WP Fastest Cache* est maintenant présente dans votre menu de gauche en bas. Cliquez dessus.
:    * Vous allez maintenant cocher un certain nombre d'options :
        * Cocher la case *Cache System*.
        * Cocher la case *Preload* puis *Homepage*, *Posts*, *Categories*, *Pages*, *Tags*, *Attachments* et *Custom Post Types*. Cliquez sur {==*Ok*==}.
        * Cocher la case *New Post*. Sélectionnez *Clear all cache*, cliquez sur {==*Ok*==}.
        * Cocher la case *Update Post*. Sélectionnez *Clear all cache*, cliquez sur {==*Ok*==}.
        * Cocher la case *Minify HTML*.
        * Cocher la case *Minify CSS*.
        * Cocher la case *Gzip*.
        * Cocher la case *Disable Emojis*.
        * Selectionnez votre langue.
:    * Cliquez sur le bouton {==*Submit*==}.

!!! success "WP Fastest Cache est correctement configuré."

***

## Really simple SSL

!!! info "Really simple SSL"

    Nous sommes sur le point d'installer Really simple SSL. Cet outil détecte automatiquement vos réglages et configure votre site web pour fonctionner en HTTPS (voir <a href="/aide/glossaire/#https" target="_blank">Glossaire</a>).


<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/ZzkqfX7SXU0?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Installation de Really simple SSL**

:    * Dans le menu de gauche, cliquez sur *Extensions*, puis sur *Ajouter une extension*.
:    * Dans la barre de recherche en haut à droite, tapez *SSL*. 
:    * Choisissez l'extension *Really simple SSL*, cliquez sur *Installer*, puis sur *Activer*.
:    * Un encart apparaît en haut de votre page. Cliquez sur le bouton bleu {==*Activer SSL !*==}.

!!! success "Really simple SSL est correctement installé."

***

## Redirection

!!! info "Redirection"

    Nous sommes sur le point d'installer Redirection qui permet de rediriger l'adresse IP (voir <a href="/aide/glossaire/#adresseip" target="_blank">Glossaire</a>) de votre serveur vers votre nom de domaine sécurisé.


<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/b20_civFPxg?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Installation de Redirection**

:    * Dans le menu de gauche, cliquez sur *Extensions*, puis sur *Ajouter une extension*.
:    * Dans la barre de recherche en haut à droite, tapez *Redirection*. 
:    * Choisissez l'extension *Really simple SSL*, cliquez sur *Installer*, puis sur *Activer*.
:    * Cliquez sur *Réglages* sous *Redirection*.
:    * Descendez en bas de la page et cliquez sur le bouton bleu {==*Start Setup*==}.
:    * Sur la page suivante, cochez les 3 cases, puis cliquez sur le bouton bleu {==*Continue Setup*==}.
:    * Sur la page suivante, sous le titre *Checking yuor REST API* toute les coches passent au vert. Si ce n'est pas le cas, cliquez sur le bouton {==*Retry*==}.
:    * Cliquez sur le bouton {==*Finish Setup*==}.
:    * Sur la page suivante, cliquez sur le bouton {==*Finished!*==}.

***

:    * Descendez en bas de la page et cochez la case *Force HTTPS*.
:    * Cliquez sur le bouton {==*Update*==}.
:    * Remontez en haut de la page et cliquez sur *Redirects*.
:    * Dans la section *Add new redirection*, écrivez **https://* dans le premier champ.
:    * Puis rendez-vous sur votre instance pour copier votre adresse IP. Collez là à la suite de *https://*. Ajoutez un */* à la fin.
:    * Dans le champ dessous, tapez l'adresse ci-dessous en remplaçant *VotreNomDeDomaine.com* par votre nom de domaine :
``` sh
https://VotreNomDeDomaine.com
```

:    * Cliquez sur le bouton {==*Add Redirect*==}.

:    * Les champs sont désormais vides, collez votre adresse IP dans le premier champ.
:    * Puis, dans le champ dessous, tapez l'adresse ci-dessous en remplaçant *VotreNomDeDomaine.com* par votre nom de domaine :
``` sh
https://VotreNomDeDomaine.com
```

:    * Cliquez sur le bouton {==*Add Redirect*==}.
:    * En haut de la page, cliquez sur *Clear Cache* puis à nouveau sur : 
        * *Delete Cache* 
        * puis *Delete Cache and Minified CSS/JS*


!!! success "Redirection est correctement installé."

***

## Velvet Blues Update URLs

!!! info "Velvet Blues Update URLs"

    Nous sommes sur le point d'installer Velvet Blues Update URLs. Si vous déplacez votre site web WordPress vers un nouveau nom de domaine, vous constaterez que les liens internes aux pages et les références aux images ne sont pas mis à jour. Ces liens et références pointeront vers votre ancien nom de domaine. Cette extension corrige ce problème en vous aidant à changer les anciennes URL et les liens de votre site Web.


<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/D0Sg4K9h0lQ?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Installation de Velvet Blues Update URLs**

:    * Dans le menu de gauche, cliquez sur *Extensions*, puis sur *Ajouter une extension*.
:    * Dans la barre de recherche en haut à droite, tapez : 
``` sh
Velvet Blues Update URLs
```

:    * Choisissez l'extension *Velvet Blues Update URLs*, cliquez sur *Installer*, puis sur *Activer*.
:    * Cliquez sur *Update URLs* sous *Velvet Blues Update URLs*.
:    * Dans le premier champ, *Old URL*, collez l'adresse ci-dessous, en remplaçant *VotreNomDeDomaine.com* par votre nom de domaine :
``` sh
http://VotreNomDeDomaine.com
```

:    * Dans le second champ, *New URL*, collez l'adresse ci-dessous, en remplaçant *VotreNomDeDomaine.com* par votre nom de domaine :
``` sh
https://VotreNomDeDomaine.com
```

:    * Cochez toutes les cases de la partie *Step 2*.
:    * Cliquez sur le bouton {==*Update URL NOW*==}.

!!! warning "Message d'erreur"

    Un message *ERROR: Something may have gone wrong.* s'affiche. C'est tout à fait normal, puisque vous n'avez en fait pas de nouveaux URLs à remplacer pour le moment. Lorsque vous créerez plus de pages, elles seront remplacées automatiquement.

!!! success "Velvet Blues Update URLs est correctement installé."

***

## Smush compression d'image et optimisation

!!! info "Smush compression d'image et optimisation"

    Nous sommes sur le point d'installer Smush. Cette extension redimensionne, optimise et compresse toutes vos images. Votre site sera ainsi plus léger et rapide.


<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/H8CmaKUlSXs?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Installation de Smush**

:    * Dans le menu de gauche, cliquez sur *Extensions*, puis sur *Ajouter une extension*.
:    * Dans la barre de recherche en haut à droite, tapez *Smush*. 
:    * Choisissez l'extension *Smush image compression and optimization*, cliquez sur *Installer*, puis sur *Activer*.
:    * Cliquez sur *Réglages* sous *Smush*.
:    * Sur la page suivante, cliquez sur le bouton bleu {==*Begin SETUP*==}.
:    * Cliquez sur la flèche de droite, cliquez à nouveau sur la flèche de droite.
:    * Décochez l'option *Allow usage data tracking*.
:    * Cliquez sur le bouton bleu {==*Finish SETUP WIZARD*==}.

!!! success "Smush est correctement installé."

***

## 11 extensions à activer

??? note "À quoi servent ces 11 extensions ?"

    **WPS Hide Login** : Généralement pour accéder à la page de connexion vous permettant d'accéder à un site Wordpress, il suffit d'ajouter */wp-login* après le nom de domaine de celui-ci. Pour des raisons de sécurité, cette application vous permet de choisir une autre terminologie pour accéder à la page de connexion à votre site. Par exemple : https://edelstom.io/entrer.<br>

    **404 page - your smart custom 404 error page** : Cette extension permet de personnaliser vos pages 404 error. Ces pages apparaissent quand un utilisateur essaye de se connecter à une page qu'il n'existe pas ou plus par exemple.<br>

    **Duplicate Page** : Vous le comprendrez plus tard, mais cette extension est très utile. Elle permet de dupliquer les pages ou articles que vous créez sur votre site.<br>

    **Force Regenerate Thumbnails** : Fait en sorte que l'affichage des photos sur votre site soit de bonne qualité.<br>

    **Loco Translate** : Vous permettra de traduire votre site. Il est également utile lors de l'utilisation de thèmes, parfois certains boutons ou liens restent dans la langue originale du thème. Cet outil permet de traduire ces détails-là dans la langue de votre choix.<br>

    **SVG Support** : Aide à l'upload de fichiers SVG sur votre site. Le format SVG est un langage XML utilisé pour décrire des graphiques en 2 dimensions. C'est à dire des images riches avec des caractéristiques telles que de la transparence, des effets de filtres et des animations.<br>

    **The SEO Framework** : Cette extension vous aidera à optimiser le SEO de votre site. Le SEO ou référencement naturel peut être défini comme un ensemble de techniques visant à de positionner un site dans les premiers résultats naturels des moteurs de recherche.<br>

    **WP Retina 2x** : Pour que votre site soit beau sur tout support, cette extension créer des fichiers images au format retina haute résolution à partir de vos photos et les affiches à vos visiteurs utilisant des appareils haute définition (High-DPI).<br>

    **Disable Gutenberg** : Permet de continuer à utiliser l'éditeur classique de Wordpress. *Gutenberg* est un nouvel éditeur qui n'est pas validé par la communauté Wordpress. Nous le désactivons donc. <br>

    **Imsanity** : Redimnsionne les images trop importante uploadées sur le site.<br>

    **Easy Updates Manager** : Permet de manager les mises à jour Wordpress. Elle rend possible, par exemple, d'empêcher les mises à jours automatiques.

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/EoMwbL-JElc?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Installation et activation des 11 extensions**

:    * Dans le menu de gauche, cliquez sur *Extensions*, puis sur *Ajouter une extension*.
:    * Dans la barre de recherche, en haut à droite, copier-coller les noms des 11 extensions ci-dessous. <br>Une fois l'extension trouvée, cliquez sur *Installer*.
``` sh
WPS Hide Login
404 page - your smart custom 404 error page
Duplicate Page
Force Regenerate Thumbnails
Loco Translate
SVG Support
The SEO Framework
WP Retina 2x
Disable Gutenberg
Imsanity
Easy Updates Manager
```

:    * Une fois toutes les extensions installées, rendez-vous dans le menu de gauche et cliquez sur *Extensions installées*.
:    * Sélectionnez toutes les extensions que vous venez d'installer. Retournez en haut de la page, cliquez sur *Actions groupées* puis sur *Activer* et enfin sur le bouton {==*Appliquer*==}.

!!! success "Vos 11 extensions sont correctement installées et activées."

***

## 7 extensions à ne pas activer tout de suite

??? note "À quoi servent ces 7 extensions?"

    **Crisp Live Chat** : Vous permettra d'installer un chat sur voter site. Vous pourrez alors interagir en direct avec vos utilisateurs.<br>

    **Ultimate Member** : Si besoin, vous pourrez créer un système de profil et membership pour accéder à certaines parties de votre site ou certains services / produits.<br>

    **GA Google Analytics** : Permet de lier votre site à Google Analytics. Vous aurez ainsi accès aux données générées par votre site, tel que le nombre de visiteurs par jour.<br>

    **Disable Comments** : Vous permettra de potentiellement supprimer toute possibilité de laisser un commentaire sur les articles de votre site.<br>

    **Mailchimp for Wordpress** : Permet de lier votre site à votre compte Mailchimp. Plus de détails plus bas.<br>

    **Mailchimp User Sync** : Aide au fonctionnement de Mailchimp avec Wordpress. <br>

    **Cookie Notice** : Génère une bannière en bas de la page d'accueil de votre site, indiquant à vos visiteurs que vous utilisez des cookies. Cette bannière est obligatoire d'après la régulation GDPR.

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/5u_JJImc-oU?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Installation des 7 extensions**

:    * Dans le menu de gauche, cliquez sur *Extensions*, puis sur *Ajouter une extension*.
:    * Dans la barre de recherche, en haut à droite, copier-coller les noms des 7 extensions ci-dessous. Nous vous avons indiqué pour certains l'auteur de l'extension pour que vous évitiez d'en sélectionner une autre similaire. <br>Une fois l'extension trouvée, cliquez sur *Installer*.
``` sh
Crisp Live Chat
Ultimate Member
GA Google Analytics (par ExactMetrics)
Disable Comments
Mailchimp for Wordpress
Mailchimp User Sync
Cookie Notice (par dFactory)
```

!!! success "Vos 7 extensions sont correctement installées."

***

## Mailchimp

!!! info "Mailchimp"

    Mailchimp est un système permettant à votre site d'envoyer des e-mails. Par exemple, vous pouvez ainsi recevoir sur votre adresse mail des notifications émanant de votre site, comme les formulaires de contacts remplis par vos utilisateurs par exemple. Vous pouvez aussi envoyer des e-mails à vos utilisateurs (notifications suite à une commande de produit, newsletter...)


<p><a href="/assets/images/wp/extentions/1.png" target="_blank"><img alt="mailchimp.com" src="/assets/images/wp/extentions/1.png"></a></p>

***

**Création d'un compte Mailchimp**

:    * Rendez-vous sur <a href="https://mailchimp.com/" target="_blank">Mailchimp.com</a>.
:    * Cliquez sur le bouton {==*Sign Up Free*==}.
:    * Complétez le fomulaire avec votre adresse e-mail, un nom pour votre compte et un mot de passe.
:    * Cliquez sur le bouton {==*Get Started!*==}.

!!! warning "N'oubliez pas de confirmer votre adresse e-mail. Mailchimp vous a envoyé un mail."

!!! success "Vous avez créé un compte Mailchimp."

***

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/TeqzQJd8qsc?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Lier votre compte Mailchimp à votre site**

:    * Sur la page *Extensions installée* cherchez les deux extensions *MailChimp for Wordpress* et *MailChimp UserSync* et activez-les.
:    * Rendez-vous au niveau de l'extension *MailChimp for Wordpress* et cliquez en dessous sur *Réglages*. Vous vous retrouvez sur la page *General Settings* de l'extension.
:    * Rendez-vous maintenant sur votre compte MailChimp.
:    * Dans le menu du haut, à droite, cliquez sur le *nom de votre compte* et dans le menu déroulant cliquez sur *Compte*.
:    * Cliquez maintenant sur *Extras* et dans le menu déroulant cliquez sur *Clés API*.
:    * Descendez un peu la page au niveau du titre *Vous n'avez pas de clé API*. Cliquez sur le bouton {==*Créer une clé*==}.
:    * Sur la page suivante, vous trouverez votre nouvelle clé API. Copiez là et retournez sur votre page Wordpress.
:    * Collez votre clé API dans le champ *Clé API*. Cliquez sur le bouton {==*Sauvgarder*==}.

!!! success "Votre compte Mailchimp est désormais lié à votre site Wordpress."

***
 
