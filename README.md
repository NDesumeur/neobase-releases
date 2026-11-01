# NeoBase

**NeoBase** est un lanceur et navigateur pour Windows, en pixel art : un accueil avec tes applis, des onglets pour le web et pour tes applis, et une boutique, **NeoStore**, d'où tu installes ce dont tu as besoin. Tout le reste (jeux, musique, bureautique, outils…) est un **plugin** que tu ajoutes ou retires quand tu veux.

## Télécharger

➡️ **[La dernière version](https://github.com/NDesumeur/neobase-releases/releases/latest)** : télécharge `NeoBase Setup x.y.z.exe` et lance-le.

NeoBase se met à jour tout seul : un bandeau sur l'accueil annonce la nouvelle version, un clic suffit.

## Ce que tu y trouves

- **Accueil et onglets** : tes sites, tes applis et tes fichiers au même endroit.
- **NeoStore** : une cinquantaine de plugins au catalogue (jeux, NeoMusic, NeoDocs / NeoSheets / NeoSlides, NeoPDF, convertisseur, paint, météo, Transports, League of Legends…), classés par catégorie, avec fiche détaillée et captures.
- **Applis système** : processus, terminal, démarrage, état du système… regroupées dans la catégorie « Système ».
- **Synchro entre tes appareils** : un seul fichier dans ton dossier cloud (OneDrive, Drive…), fusionné sans rien écraser. Les plugins y mettent aussi leurs données.
- **Sécurité** : chaque plugin est vérifié (signature, empreinte, antivirus), demande ses autorisations et peut les perdre à tout moment (écran Autorisations). Un plugin retiré du catalogue est désinstallé.

## Les plugins

| | |
|---|---|
| **Le catalogue officiel** | [neobase-store-catalog](https://github.com/NDesumeur/neobase-store-catalog) : la liste des plugins approuvés (et des retirés). |
| **Créer un plugin** | [neobase-sdk](https://github.com/NDesumeur/neobase-sdk) : le format `plugin.json`, l'API (`ctx`, dossier de données, synchro, volet système), le schéma de validation, un exemple et le [guide de publication](https://github.com/NDesumeur/neobase-sdk/blob/main/docs/PUBLIER.md). |
| **Tous les plugins** | [les dépôts `neobase-plugin-*`](https://github.com/search?q=topic%3Aneobase-plugin&type=repositories) : un dépôt par plugin, avec ses Releases. |

Tu peux publier ton propre plugin : un dépôt GitHub avec le sujet `neobase-plugin` et une Release suffisent, NeoStore le propose alors comme plugin « non vérifié ». Les plugins officiels sont signés par NeoBase.

## Ce dépôt

Il ne contient que les installateurs (onglet **Releases**) et sert aux mises à jour automatiques : ne le renomme pas et ne supprime pas ses Releases, les NeoBase déjà installés y vont chercher leur mise à jour.

Le code de NeoBase lui-même est privé.
