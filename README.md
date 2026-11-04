# NeoBase

**NeoBase** est un lanceur et navigateur pour Windows. Il regroupe sur un même accueil :
- tes sites, tes applis et tes fichiers ;
- des onglets pour le web comme pour les applis ;
- une boutique, **NeoStore**, où tu installes ce dont tu as besoin.

Tout le reste (jeux, musique, bureautique, outils…) est un **plugin** que tu ajoutes ou retires quand tu veux. Chaque plugin ne reçoit que les droits que tu lui donnes.

## Télécharger

➡️ **[La dernière version](https://github.com/NDesumeur/neobase-releases/releases/latest)** : télécharge `NeoBase Setup x.y.z.exe` et lance-le.

NeoBase se met à jour tout seul. Un bandeau sur l'accueil annonce la nouvelle version, et un clic suffit.

## Ce que tu y trouves

**Accueil**
- Tes raccourcis classés par catégories et favoris.
- Un tri en un clic : de A à Z, de Z à A, les catégories les plus remplies d'abord.

**Navigateur**
- Des onglets, avec fenêtres privées sans historique ni cookies.
- Un bloqueur de publicités et de traqueurs, YouTube compris.
- Un gestionnaire de mots de passe et des autorisations par site (caméra, micro, position…).
- Un VPN intégré :
  - **Cloudflare WARP** pour chiffrer ta connexion ;
  - **Tor** pour sortir par le pays de ton choix (États-Unis, Royaume-Uni, Allemagne, Pays-Bas, Suisse, Suède, Canada, Japon).

**NeoStore**
- Une soixantaine de plugins classés par catégorie, avec fiche détaillée, captures et autorisations demandées. Par exemple :
  - NeoMusic ;
  - NeoDocs / NeoSheets / NeoSlides, NeoPDF ;
  - un convertisseur de fichiers, un éditeur d'images ;
  - la météo, les transports ;
  - des jeux.

**Centre de notifications**
- NeoBase et les plugins t'y préviennent.
- Non lues en badge, et un clic ouvre ce que la notification désigne.

**Synchro entre tes appareils**
- Un seul fichier dans ton dossier cloud (OneDrive, Drive…), fusionné sans rien écraser.
- Les plugins y rangent aussi leurs données.
- En cas de conflit, c'est toi qui choisis la version à garder.

**Applis système** : processus, terminal, démarrage, état du système, sauvegardes.

## Sécurité

**Plugins vérifiés**
- Les plugins officiels sont examinés, puis signés (ed25519) avec une clé qui n'est stockée dans aucun dépôt.
- Avant d'installer, NeoBase vérifie la signature, l'empreinte SHA-256 de l'archive et passe l'antivirus.

**Autorisations précises**
- Elles viennent d'un registre public unique ([permissions.json](https://github.com/NDesumeur/neobase-sdk/blob/main/permissions.json)).
- Chaque plugin ne demande que ce dont il a besoin :
  - ses données (sans plafond pour un plugin signé, 1 Go pour un plugin non vérifié) ;
  - Internet, limité à certains domaines ;
  - les données d'un autre plugin, en lecture ou en écriture séparément, et seulement si cet autre plugin les partage ;
  - les programmes autorisés, d'une liste blanche.
- NeoBase contrôle chaque appel. Un appel non autorisé est refusé (`PERMISSION_DENIED`).

**Tu gardes la main**
- L'écran **Autorisations** montre tout, par plugin ou par autorisation :
  - le niveau de risque en couleur ;
  - la dernière utilisation ;
  - les combinaisons à surveiller.
- Tu peux tout couper, désactiver un plugin ou le remettre à zéro.
- Une autorisation se demande au moment où elle sert, avec la raison : « cette fois » ou « toujours ».

**Mises à jour sous contrôle** : une mise à jour qui demande plus de droits attend ton accord. D'ici là, l'ancienne version reste en place.

**Isolation**
- Les plugins non signés tournent dans un bac à sable, dans leur propre processus. S'ils plantent, NeoBase continue.
- Les sites web s'ouvrent sans aucun accès à NeoBase.

**Electron durci**
- `contextIsolation`, `sandbox`, `nodeIntegration` coupé.
- Une politique de sécurité du contenu (CSP) qui interdit tout script venu d'Internet dans NeoBase.

**Révocation rapide** : un plugin retiré du catalogue est désinstallé de tous les PC en 15 minutes environ.

**Pas de droits administrateur** : NeoBase n'en demande jamais.

Une faille ? Lis la [politique de sécurité](https://github.com/NDesumeur/neobase-store-catalog/blob/main/SECURITY.md) et signale-la en privé.

## Les plugins

| | |
|---|---|
| **Le catalogue officiel** | [neobase-store-catalog](https://github.com/NDesumeur/neobase-store-catalog) : la liste des plugins approuvés et des plugins retirés. |
| **Créer un plugin** | [neobase-sdk](https://github.com/NDesumeur/neobase-sdk) : le format `plugin.json`, le registre des autorisations, l'API (`ctx`, dossier de données, notifications, synchro, volet système), le schéma de validation, un exemple et le [guide de publication](https://github.com/NDesumeur/neobase-sdk/blob/main/docs/PUBLIER.md). |
| **Tous les plugins** | [les dépôts `neobase-plugin-*`](https://github.com/search?q=topic%3Aneobase-plugin&type=repositories) : un dépôt par plugin, avec ses Releases. |

Tu peux publier ton propre plugin : il suffit d'un dépôt GitHub avec le sujet `neobase-plugin` et d'une Release. NeoStore le propose alors comme plugin « non vérifié », dans le bac à sable.

## Ce dépôt

Il ne contient que les installateurs (onglet **Releases**) et sert aux mises à jour automatiques. Ne le renomme pas et ne supprime pas ses Releases : les NeoBase déjà installés y vont chercher leur mise à jour.

Le code de NeoBase lui-même est privé.
