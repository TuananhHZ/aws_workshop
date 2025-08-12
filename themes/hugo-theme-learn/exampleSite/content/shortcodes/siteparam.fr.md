---
title: Site param
description : "Afficher la valeur d'un paramÃ¨tre global du site dans votre page"
---

Les shortcode `siteparam` est utilisÃ© pour vous aider Ã  afficher des valeurs provenant des paramÃ¨tres globaux du site. 

Par exemple, dans ce site, le paramÃ¨tre `editURL`  est utilisÃ© dans le fichier `config.toml`

```toml
[params]
  editURL = "https://github.com/matcornic/hugo-theme-learn/edit/master/exampleSite/content/"
```

Utilisez le shortcode `siteparam` pour affichier sa valeur.

```
Valeur de `editURL` : {{%/* siteparam "editURL" */%}}
```

s'affiche comme

Valeur de `editURL` : {{% siteparam "editURL" %}}
