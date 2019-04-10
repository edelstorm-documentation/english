# Création de l'instance <small>- Lightsail</small>

!!! tip "Copiez / collez facilement les commandes du tutoriel en cliquant sur l'icône de droite."

    ``` sh
    Copiez cette phrase pour tester.
    ```

## Générer une paire de clés SSH<a href="/aide/glossaire/#ssh"" target="_blank">&#185;</a>

<p><a href="../assets/images/aws/creation-instance/fr/1.gif" target="_blank"><img alt="Générer une paire de clé SSH sur Mac" src="../assets/images/aws/creation-instance/fr/1.gif"></a></p>

***

**Sécurisation des communications entre votre ordinateur et votre futur serveur**

:    * {==Pour les ordinateurs Mac==} En haut à droite de votre écran, lancez une recherche Spotlight en cliquant sur la loupe. Tapez ***Terminal*** puis appuyez sur <kbd>Entrer</kbd>.
:    * {==Pour les ordinateurs Windows==} Plusieurs solutions en fonction de la version de votre OS. 
        * Soit, dans le menu *Démarrer*, tapez dans la barre de recherche ***cmd***. <br>
        Sélectionnez le premier résultat ( *Command Prompt* ), en faisant un clic droit puis sélectionnez : *exécuter en tant qu'administrateur*.
        * Soit, ouvrez la barre de recherche de l'ordinateur en cliquant sur votre bureau (cliquez sur votre fond d'écran) puis en appuyant en même temps sur les touches <kbd>⊞Win</kbd> et <kbd>S</kbd>. <br>
        Tapez : ***cmd*** dans le champ de recherche. Sélectionnez le premier résultat ( *Command Prompt* ), en faisant un clic droit puis sélectionnez : *exécuter en tant qu'administrateur*.

:    * Une fois dans votre <a href="/aide/glossaire/#terminal" target="_blank">terminal</a>, tapez la commande ci-dessous et appuyez sur <kbd>Entrer</kbd>.
``` sh
ssh-keygen -t rsa
```

:    * Vous pouvez ensuite nommer votre paire de clés, sinon appuyez juste sur <kbd>Entrer</kbd>.
:    * Une petite clé s'affiche. Il est temps de définir un mot de passe {==(voir note ci-dessous)==} et appuyez sur <kbd>Entrer</kbd>.
:    * Ressaisissez votre mot de passe et appuyez sur <kbd>Entrer</kbd>.

!!! note "À savoir"

    Lorsque vous tapez votre mot de passe dans un terminal, vous ne **pourrez pas le voir se former sur votre écran**.<br>
    C'est **comme si vous n'étiez pas en train de taper sur votre clavier**, mais pour le terminal vous êtes bien en train de taper. Vous devez donc le définir à l'aveugle !

***

<p><a href="../assets/images/aws/creation-instance/fr/2.gif" target="_blank"><img alt="Localiser une paire de clé SSH sur Mac" src="../assets/images/aws/creation-instance/fr/2.gif"></a></p>

***

**Localisation de votre paire de clés SSH<a href="/aide/glossaire/#ssh" target="_blank">&#185;</a>**

{==Pour les ordinateurs Mac==} 
:    * Ouvrez votre Finder, cliquez en haut dans la barre de menu sur **Aller**, puis cliquez sur **Aller au dossier...**
:    * Dans la barre de recherche, tapez cette commande et appuyez sur <kbd>Entrer</kbd>.
``` sh
~/.ssh
```

:    * Une fois dans le dossier {==.ssh==} faites glisser l'icône dossier en haut de la fenêtre du Finder dans votre barre de favoris. Cela vous permettra d'y accéder plus facilement pour la prochaine étape.

{==Pour les ordinateurs Windows==} 
:    * 
:    * 

!!! success "Votre machine a généré votre paire de clés SSH que vous pouvez facilement localiser à partir de son dossier !"

***

## Création de l'instance

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/gF4tAzemagk?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Options de l'instance Amazon Lightsail**

:    * **Retournez sur votre navigateur web**. Vous avez normalement laissé votre fenêtre AWS zone hébergée ouverte (voir étape précédente <a href="/nom-de-domaine/" target="_blank">Nom de domaine</a>). <br>
Faites un clic droit sur le logo ***AWS*** à droite et ouvrez dans un nouvel onglet. 

:    * Vous vous retrouvez sur votre console de management AWS. Cherchez le service ***Lightsail*** dans la barre recherche et cliquez dessus.
:    * Définissez la langue que vous souhaitez utiliser pour l'interface.
:    * Cliquez sur {==Créer une instance==}.
:    * **Choisissez l'emplacement de l'instance.** Choisissez la région se rapprochant le plus de vos futurs utilisateurs.<br>
        *Si vous ciblez un public européen francophone, vous pouvez choisir Paris, si vous ciblez des utilisateurs japonais, choisissez Tokyo... Le but est de permettre à vos utilisateurs de charger plus rapidement votre site.*
:    * Laissez la zone de disponibilité de l'instance par défaut.
:    * Choisissez ***Linux/Unix*** comme plateforme.
:    * Dans : *Sélectionner un plan*, cliquez sur l'onglet ***Système d'exploitation uniquement***, puis sélectionnez ***Ubuntu 18.04 LTS*** comme système d'exploitation.
:    * Nous n'ajouterons pas de script de lancement. (voir <a href="/aide/glossaire/#script-de-lancement" target="_blank">glossaire</a>.)
:    * Cliquez sur ***Modifier une paire de clés SSH*** et cliquez sur ***Charger un nouveau*** puis sur {==Charger==}. 
:    * Cliquez sur ***Choisir un fichier*** et choisissez le fichier `id_rsa.pub` dans votre dossier `~/.ssh` puis cliquez sur {==Charger une clé==}.<br>
*Le chargement peut prendre quelques minutes.*<br> 
*Fournir votre clé SSH publique vous permettra de sécuriser les communications entre votre machine et votre instance Amazon Lightsail.*

:    * Choisissez le plan d'instance basique à **3.50$ par mois**, le premier mois d'essais est gratuit.
:    * Nommez votre instance, de préférence avec votre <a href="/aide/glossaire/#nom-de-domaine" target="_blank">nom de domaine</a>.
:    * Vous pouvez appliquer des balises d'identifications à cette instance si vous pensez en créer plusieurs par la suite.
:    * Cliquez sur {==Créer une instance==} et patientez un instant que votre instance s'initialise.

!!! info "Informations"

    À partir de cette étape, vous souscrivez au service Amazon Lighsail. Vous pouvez supprimer cette instance à tout moment si vous n'en avez plus besoin. Consultez l'évolution de votre facturation depuis votre <a href="https://console.aws.amazon.com/billing/home#/" target="_blank">console de management AWS</a>.

!!! success "Votre instance Amazon Lightsail est prête à être utilisée pour votre site web."

***

## Firewall & IP Statique

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/Y8-gIGv1zW4?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Ouverture des ports HTTPS & FTP**

:    * L'encart de votre instance est passée de gris à orange. Elle est donc prête à être utilisée.
:    * Cliquez sur l'instance, ou plus précisément sur le ***nom de votre instance***, puis cliquez sur l'onglet ***Mise en réseau***.
:    * Descendez la page jusqu'à la section *Par-feu*, cliquez sur ***Ajouter un autre élément***.
:    * Dans le champ *Personnaliser* cliquez sur le menu déroulant et sélectionnez : ***HTTPS***.<br>
        *Cette étape permet de sécuriser les communications entre vos utilisateurs, les applications externes et votre instance. <a href="/aide/glossaire/#https" target="_blank">Cliquez ici pour en savoir plus sur le https</a>.*
:    * Cliquez sur ***Ajouter un autre élément***.
:    * Préoccupez-vous uniquement du dernier champ *Plage de ports* et ajoutez le port suivant ***34210***.
:    * Cliquez sur {==Enregistrer==}.

***

**Fixation de l'adresse IP dynamique**

:    * Remontez un peu la page et cliquez sur {==Créer une IP Statique==}.
:    * L'emplacement de l'IP Statique doit être similaire à celui de votre instance.
:    * Dans *Identifiez votre adresse IP statique*, nommez votre IP statique de la façon suivante, mais avec VOTRE nom de domaine complet :
``` sh
StaticIp-VotreNomDeDomaine
```

:    * Cliquez sur {==Créer==}.

!!! info "Informations"

    Par défaut, votre instance a une adresse IP dynamique. C'est-à-dire qu'à chaque fois que vous redémarrez votre instance, son adresse IP change. Pour que votre site web soit joignable depuis une adresse unique, il faut lier votre instance à une IP statique. Une <a href="/aide/glossaire/#ip-statique" target="_blank">IP statique</a> est gratuite lorsqu'elle est attachée à une instance.

!!! success "Les ports HTTPS et FTP sont ouvert et votre instance Lightsail possède une adresse IP statique."

***

## Zone DNS

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/sixUu-dGwVo?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Association de votre instance à votre nom de domaine**

:    * En haut à gauche, cliquez sur ***Accueil*** puis sur l'onglet ***Mise en réseau***.
:    * Cliquez sur {==Créer une zone DNS==}. <a href="/aide/glossaire/#zone-dns" target="_blank">Cliquez ici pour en savoir plus sur la zone DNS</a>.
:    * Dans le premier champ, spécifiez votre nom de domaine.
:    * Vous pouvez associer des tags d'identifications à cette zone DNS si vous pensez en créer plusieurs par la suite.
:    * Cliquez sur {==Créer une zone DNS==}

***

**Création des enregistrements pour votre zone DNS**

:    * Cliquez sur ***Ajouter un enregistrement***.
:    * Ajoutez un premier enregistrement de type A pour `@.VotreNomDeDomaine.com` pointant vers votre IP statique. <br><br>
       **Pour se faire**, tapez <kbd>@</kbd> dans le 1er champ qui se présente à vous à gauche. Puis sélectionnez à droite l'adresse IP statique que nous venons de créer. Cliquez sur l'***icone verte*** pour valider cette action.
:    * Cliquez à nouveau sur ***Ajouter un enregistrement***
:    * Ajoutez un second enregistrement de type A pour `www.VotreNomDeDomaine.com` pointant vers votre IP statique.<br><br>
       **Pour se faire**, tapez <kbd>www</kbd> dans le 1er champ qui se présente à vous à gauche. Puis sélectionnez à droite l'adresse IP statique que nous venons de créer. Cliquez sur l'***icone verte*** pour valider cette action.<br>

:    * **La prochaine étape vous sert à enregister un <a href="/aide/glossaire/#sous-domaine" target="_blank">sous-domaine</a>**, si vous avez besoin de créer un e-shop par exemple. Ce n'est donc pas une étape obligatoire et vous pourrez ajouter un sous-domaine plus tard. Cependant, l'ajout sera alors payant via Runcloud (voir la video).
:    * Ajoutez un troisième enregistrement de type A pour `SousDomaine.VotreNomDeDomaine.com` pointant vers votre IP statique.<br><br>
       **Pour se faire**, tapez <kbd>VotreSousDomaine</kbd> dans le 1er champ qui se présente à vous à gauche. Puis sélectionnez à droite l'adresse IP statique que nous venons de créer. Cliquez sur l'***icone verte*** pour valider cette action.

!!! success "Votre instance possède une zone DNS et son IP statique pointe vers votre nom de domaine."

***

## Serveurs de Noms

<iframe width="100%" height="405" src="https://www.youtube-nocookie.com/embed/44dl6vCcAmU?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture setPlaybackQuality(hd1080);" allowfullscreen></iframe>

***

**Injection des serveurs de noms pour votre nom de domaine**

:    * Sous les enregistrements de la zone DNS se trouve une section *Serveurs de noms*.
:    * Retournez sur la page *Route 53* que vous avez laissée ouverte.<br>
Si vous l'avez fermé, faites un clique droit, ouvrir dans un nouvel onglet sur ***AWS*** haut à droite de votre page. Une fois sur votre console, cherchez *Route 53* dans la barre de recherche et cliquez dessus.

:    * Dans le menu de gauche, cliquez sur ***Domaines enregistrés***.
:    * Cliquez sur votre ***nom de domaine***.
:    * Sur la droite, cliquez sur ***Ajouter/Modifier les noms de serveurs***.<br>
Vous devez maintenant remplacer un à un les serveurs de noms actuels, par les quatre nouveaux noms de serveurs de votre zone DNS. Vous pouvez les retrouver sur la page Lightsail que vous venez de quitter.

:    * Cliquez sur {==Mettre à jour==}.
:    * Dans le menu de gauche, cliquez sur ***Tableau de bord***.
:    * Regardez le tableau de l'encart *Alertes*. Vous pouvez voir sur la première ligne que vos serveurs de noms sont en cours de mise à jour.
:    * Attendez quelques minutes puis rafraîchissez la page. 
:    * Il est désormais indiqué que vos serveurs de noms ont été correctement mis à jour.

!!! success "Les noms des serveurs de votre zone DNS correspondent à votre nom de domaine."

***

## Options de l'instance

!!! info "Tour d'horizon"

    Vous venez de créer votre première instance. En cliquant sur son nom depuis l'accueil, vous pourrez découvrir de nombreuses options que nous allons vous présenter ci-dessous.

<p><a href="../assets/images/aws/creation-instance/fr/3.png" target="_blank"><img alt="Options Instance Amazon Lightsail" src="../assets/images/aws/creation-instance/fr/3.png"></a></p>

***

**Connexion SSH depuis votre navigateur**

:    * Dans l'onglet *Connexion*, en cliquant sur *Se connecter à l'aide de SSH* vous pourrez accéder en mode sécurisé au terminal de votre serveur à distance.
:    * Vous pouvez choisir de vous connecter, d'arrêter, de redémarrer et de supprimer cette instance.
:    * Vous pouvez utiliser votre IP statique et nom d'utilisateur affichés ici, si vous souhaitez vous connecter en SSH directement avec le terminal de votre ordinateur.

!!! info "<a href="/aide/glossaire/#ssh" target="_blank">Cliquez ici</a> pour en savoir plus sur le SSH."

***

<p><a href="../assets/images/aws/creation-instance/fr/4.png" target="_blank"><img alt="Connexion SSH Instance Amazon Lightsail" src="../assets/images/aws/creation-instance/fr/4.png"></a></p>

***

**Stockage évolutif**

:    * Dans l'onglet *Stockage*, avec le plan à 3.50$ par mois vous bénéficiez de 20Go de stockage sur cette instance. Ce qui est largement suffisant pour vos besoins actuels.
:    * Si vous avez besoin de plus d'espace de stockage, vous pouvez ajouter des disques supplémentaires à cette instance. L'ajout de nouveaux disques est une fonction payante.

***

<p><a href="../assets/images/aws/creation-instance/fr/5.png" target="_blank"><img alt="Stockage Évolutif Instance Amazon Lightsail" src="../assets/images/aws/creation-instance/fr/5.png"></a></p>

***

**Métriques**

:    * Dans l'onglet *Métriques*, vous pouvez obtenir les statistiques basées sur l'usage que vous faites de votre instance.

***

<p><a href="../assets/images/aws/creation-instance/fr/6.png" target="_blank"><img alt="Métriques Instance Amazon Lightsail" src="../assets/images/aws/creation-instance/fr/6.png"></a></p>

***

**Snapshots**

:    * L'onglet *Snapshots* est une fonctionnalité très importante sur laquelle nous reviendrons par la suite. Un snapshot vous permet de sauvegarder la totalité de votre instance (et donc votre site) à un instant T. Cela peut donc vous permettre de revenir à une version antérieure de votre instance en cas d'erreur.

***

<p><a href="../assets/images/aws/creation-instance/fr/7.png" target="_blank"><img alt="Snapshots Instance Amazon Lightsail" src="../assets/images/aws/creation-instance/fr/7.png"></a></p>

***

**Tags**

:    * Vous pouvez ajouter des tags à votre instance pour l'identifier plus facilement, si vous en avez plusieurs.

***

<p><a href="../assets/images/aws/creation-instance/fr/8.png" target="_blank"><img alt="Tags Instance Amazon Lightsail" src="../assets/images/aws/creation-instance/fr/8.png"></a></p>

***

**Historique**

:    * Vous pouvez consulter l'historique pour voir vos dernières actions sur cette instance.

***

<p><a href="../assets/images/aws/creation-instance/fr/9.png" target="_blank"><img alt="Historique Instance Amazon Lightsail" src="../assets/images/aws/creation-instance/fr/9.png"></a></p>

***

**Suppression**

:    * À tout moment, vous pouvez supprimer votre instance depuis cet onglet.

***

!!! success "Félicitation votre instance est configurée pour votre site web !"