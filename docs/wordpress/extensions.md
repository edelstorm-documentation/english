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

    Nous sommes sur le point d'installer WP Fastest Cache. A QUOI CA SERT.


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

    Nous sommes sur le point d'installer Really simple SSL. A QUOI CA SERT.


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

    Nous sommes sur le point d'installer Redirection. A QUOI CA SERT.


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

    Nous sommes sur le point d'installer Velvet Blues Update URLs. A QUOI CA SERT.


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

    Nous sommes sur le point d'installer Smush. A QUOI CA SERT.


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