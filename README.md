# aincradbot-legal

Documents légaux publics d'**AincradBot**, le bot Discord de la communauté AincradMC.

Ce dépôt existe uniquement pour donner une **URL publique** aux deux documents exigés par la vérification d'une application Discord. Le code source du bot est hébergé séparément, dans un dépôt privé.

## Pages publiées

- https://deonata.github.io/aincradbot-legal/conditions-utilisation
- https://deonata.github.io/aincradbot-legal/politique-confidentialite

## Mise à jour

Les fichiers de référence vivent dans le dépôt du bot, sous `docs/`. Après les avoir modifiés là-bas :

```bash
cp ../AincradBot/docs/*.md .
sed -i 's/(conditions-utilisation\.md)/(conditions-utilisation)/g; s/(politique-confidentialite\.md)/(politique-confidentialite)/g' *.md
git commit -am "Mise a jour des documents legaux"
git push
```

Le `sed` retire l'extension des liens internes : GitHub Pages sert les fichiers Markdown en `.html`, un lien vers `.md` renverrait donc une erreur 404.
