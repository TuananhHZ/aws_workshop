---
title: "Learn Theme for Hugo"
---

# ThÃ¨me Hugo learn

[Hugo-theme-learn](http://github.com/matcornic/hugo-theme-learn) est un thÃ¨me pour [Hugo](https://gohugo.io/), un gÃ©nÃ©rateur de site statique, rapide et modern, Ã©crit en Go. Tandis que Hugo est souvent utilisÃ© pour des blogs, ce thÃ¨me multi-langue est **entiÃ¨rement conÃ§u pour la documentation**.

Ce thÃ¨me est un portage partiel du [thÃ¨me Learn](http://learn.getgrav.org/) de [Grav](https://getgrav.org/), un CMS modern Ã©crit en PHP.

{{% notice tip %}}Le thÃ¨me Learn fonctionne grÃ¢ce Ã  la structure de page aborescentes pour organiser le contenu: tous les contenus sont des pages qui appartiennent Ã  d'autres pages. [Plus d'infos]({{%relref "cont/pages/_index.md"%}}) 
{{% /notice %}}

## FonctionnalitÃ©s principales

* [Recherche automatique]({{%relref "basics/configuration/_index.md#activer-recherche" %}})
* [Mode multi-langue]({{%relref "cont/i18n/_index.md" %}})
* **Nombre de niveau infini dans le menu**
* **Boutons suivant/prÃ©cÃ©dent automatiquement gÃ©nÃ©rÃ©s pour naviguer entre les items du menu**
* [Taille d'image, ombres...]({{%relref "cont/markdown.fr.md#images" %}})
* [Fichiers joints]({{%relref "shortcodes/attachments.fr.md" %}})
* [Lister les pages filles]({{%relref "shortcodes/children/_index.md" %}})
* [Diagrammes Mermaid]({{%relref "shortcodes/mermaid.fr.md" %}}) (flowchart, sequence, gantt)
* [Style configurable and variantes de couleurs]({{%relref "basics/style-customization/_index.md"%}})
* [Boutons]({{%relref "shortcodes/button.fr.md" %}}), [Messages Astuce/Note/Info/Attention]({{%relref "shortcodes/notice.fr.md" %}}), [Expand]({{%relref "shortcodes/expand.fr.md" %}})

![Screenshot](https://github.com/matcornic/hugo-theme-learn/raw/master/images/screenshot.png?width=40pc&classes=shadow)

## Contribuer Ã  cette documentation

N'hÃ©sitez pas Ã  mettre Ã  jour ce contenu en cliquant sur le lien **Modifier cette page** en haut de chaque page, et crÃ©er la Pull Request associÃ©e.

{{% notice info %}}
Votre modification sera dÃ©ployÃ©e automatiquement quand elle sera mergÃ©e.
{{% /notice %}}

## Site de documentation

Cette documentation statique a Ã©tÃ© gÃ©nÃ©rÃ©e avec Hugo avec une simple commande : `hugo -t hugo-theme-learn` -- le code source est [disponible sur Github](https://github.com/matcornic/hugo-theme-learn)

{{% notice note %}}
Le site est auomatiquement publiÃ© et hÃ©bergÃ© par [Netlify](https://www.netlify.com/). Plus d'infos sur le [dÃ©ploiement de site Hugo avec Netlify](https://www.netlify.com/blog/2015/07/30/hosting-hugo-on-netlifyinsanely-fast-deploys/)(En anglais)
{{% /notice %}}
