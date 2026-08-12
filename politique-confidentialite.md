# Politique de Confidentialité — AincradBot

**Dernière mise à jour : 12 août 2026**

Ce document explique quelles données AincradBot traite, pourquoi, combien de temps, et comment en demander la suppression. Il décrit le fonctionnement réel du bot, pas un modèle générique.

---

## 1. Responsable du traitement

Le bot est auto-hébergé par l'équipe **AincradMC** sur un serveur privé situé dans l'Union européenne. Aucune donnée n'est confiée à un prestataire d'hébergement tiers pour le bot lui-même.

**Contact :** `contact@aincradmc.fr`

## 2. Principe général

AincradBot ne conserve **que le strict nécessaire à son fonctionnement**. En particulier :

- **le contenu de vos messages n'est jamais enregistré** en base de données ;
- **aucune donnée n'est vendue, louée, ni utilisée à des fins publicitaires** ;
- **aucun traceur, aucun outil d'analyse d'audience** n'est utilisé ;
- les données sont **cloisonnées par serveur Discord** : un serveur ne voit jamais les données d'un autre.

## 3. Données enregistrées

Toutes les données ci-dessous sont stockées dans une base SQLite locale, sur le serveur d'hébergement.

### 3.1 Identifiants

| Donnée | Finalité |
|---|---|
| Identifiant Discord de l'utilisateur | Rattacher une progression, un avertissement ou une participation à la bonne personne |
| Identifiant du serveur, des salons et des rôles | Appliquer la configuration au bon endroit |

Les identifiants Discord sont des numéros publics, attribués par Discord. Le bot ne stocke ni votre adresse e-mail, ni votre numéro de téléphone, ni votre mot de passe, ni vos moyens de paiement — il n'y a d'ailleurs jamais accès.

### 3.2 Système de niveaux

Points d'expérience, niveau atteint, nombre de messages envoyés, minutes passées en vocal, date du dernier gain, statut d'exclusion du classement.

**Finalité :** faire fonctionner la progression et le classement.
Le **nombre** de messages est compté ; leur **contenu** n'est pas conservé.

### 3.3 Modération

Avertissements (auteur, modérateur, motif, date, date d'expiration) et historique des sanctions (avertissement, exclusion temporaire, expulsion, bannissement, suppression de messages).

**Finalité :** appliquer les sanctions progressives et permettre au staff de consulter un historique.

Lorsqu'une action automatique est déclenchée, un extrait du message concerné peut être **envoyé dans un salon de logs Discord** choisi par les administrateurs. Ce message est alors hébergé par Discord et soumis à sa propre politique de conservation ; le bot n'en garde pas de copie.

### 3.4 Suggestions

Identifiant du fil de discussion, identifiant de l'auteur, titre de la suggestion, extrait du message d'origine (500 caractères maximum), votes (qui a voté pour ou contre), nombre de commentaires, statut, réponse du staff.

**Finalité :** classer les suggestions par popularité, empêcher les votes multiples et produire le récapitulatif public.

### 3.5 Autres fonctions

| Fonction | Données |
|---|---|
| Salons vocaux temporaires | Identifiant du salon et de son propriétaire, date de création |
| Tirages au sort | Liste des participants, date de participation, gagnants tirés |
| Panneaux de rôles | Rôles proposés, sans historique individuel d'attribution |
| Configuration | Réglages, listes de mots filtrés, réponses automatiques, identifiants de salons |

## 4. Données traitées sans être enregistrées

Certaines données transitent en mémoire vive le temps d'un traitement, puis disparaissent :

- **Contenu des messages** — analysé par la modération automatique (mots filtrés, liens, spam, majuscules, mentions) puis immédiatement écarté. Rien n'est écrit sur disque.
- **Images jointes** — lorsque l'analyse anti-arnaque par reconnaissance de texte est activée, les images sont téléchargées temporairement en mémoire, analysées, puis effacées. Elles ne sont ni stockées, ni transmises à un tiers : la reconnaissance de texte s'exécute **localement** sur le serveur d'hébergement.

## 5. Services tiers

| Service | Données transmises | Finalité |
|---|---|---|
| **Discord** | Toutes les interactions, par nature | Fonctionnement du bot — voir la [politique de Discord](https://discord.com/privacy) |
| **api.mcsrvstat.us** | Adresse du serveur Minecraft uniquement | Afficher le statut du serveur de jeu |
| **raw.githubusercontent.com** | Aucune donnée personnelle | Télécharger la liste publique de domaines frauduleux |

**Aucune donnée personnelle d'utilisateur n'est transmise à un service tiers.**

## 6. Durée de conservation

| Donnée | Conservation |
|---|---|
| Avertissements | 30 jours par défaut, puis inactifs ; paramétrable par serveur |
| Historique des sanctions | Jusqu'à suppression manuelle par le staff ou demande de l'utilisateur |
| Niveaux et statistiques | Tant que le bot est présent sur le serveur |
| Salons vocaux temporaires | Supprimés en même temps que le salon, quelques secondes après son abandon |
| Tirages au sort | Conservés à des fins de vérification, puis supprimables sur demande |
| Suggestions | Tant que le serveur les conserve |

**Retrait du bot du serveur :** les données du serveur concerné deviennent inutilisées. Leur suppression définitive peut être demandée à tout moment via le contact indiqué et sera effectuée sous 30 jours.

## 7. Vos droits

Conformément au Règlement général sur la protection des données (RGPD), vous disposez d'un droit d'**accès**, de **rectification**, d'**effacement**, de **limitation**, d'**opposition** et de **portabilité** de vos données.

Pour l'exercer, écrivez à `contact@aincradmc.fr` ou contactez un administrateur sur le serveur Discord AincradMC, en précisant votre identifiant Discord.

Une réponse vous sera apportée sous **30 jours**. Certaines demandes d'effacement peuvent être refusées lorsque la conservation est nécessaire à la sécurité du serveur — par exemple l'historique d'un bannissement pour harcèlement.

Vous pouvez également introduire une réclamation auprès de la **CNIL** (www.cnil.fr).

## 8. Base légale

Le traitement repose sur l'**intérêt légitime** des administrateurs de serveur à assurer la modération, la sécurité et l'animation de leur communauté, ainsi que sur le **consentement** que vous exprimez en rejoignant un serveur où le bot est présent et en utilisant ses fonctions.

## 9. Sécurité

- La base de données est stockée sur un serveur privé, accessible uniquement par authentification par clé.
- Le bot s'exécute sous un compte système non privilégié, isolé du reste du serveur.
- Le jeton d'authentification Discord est stocké dans un fichier à accès restreint, exclu du dépôt de code.
- Les sauvegardes sont conservées localement et purgées automatiquement.

Aucun système n'étant infaillible, une sécurité absolue ne peut être garantie.

## 10. Mineurs

Le bot suit les règles d'âge de Discord. Aucune donnée n'est sciemment collectée auprès d'une personne n'ayant pas l'âge minimum requis. Si vous constatez qu'un tel cas s'est produit, signalez-le au contact ci-dessus : les données seront supprimées.

## 11. Modifications

Cette politique peut évoluer. La date de dernière mise à jour figure en tête de document. Les changements significatifs seront annoncés sur le serveur Discord AincradMC.

## 12. Contact

- **E-mail :** `contact@aincradmc.fr`
- **Discord :** serveur AincradMC

---

*Ce document décrit les pratiques réelles du service. Il ne constitue pas un avis juridique.*
