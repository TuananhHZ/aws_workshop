---
title: Installation
weight: 15
---

Les Ã©tapes suivantes sont lÃ  pour vous aider Ã  initialiser votre site. Si vous ne connaissez pas du tout Hugo, il est fortement conseillÃ© de vous entrainer en suivant ce [super tuto pour dÃ©butants](https://gohugo.io/overview/quickstart/).

## CrÃ©er votre projet

Hugo fournit une commande `new` pour crÃ©er un nouveau site.

```
hugo new site <new_project>
```

## Installer le thÃ¨me

Installer le thÃ¨me **Hugo-theme-learn** en suivant [cette documentation](https://gohugo.io/themes/installing/)

Le repo du thÃ¨me est : https://github.com/matcornic/hugo-theme-learn.git

Sinon, vous pouvez [tÃ©lÃ©charger le thÃ¨me sous forme d'un fichier .zip](https://github.com/matcornic/hugo-theme-learn/archive/master.zip) et extrayez le dans votre dossier de thÃ¨mes.

## Configuration simple

Lorsque vous gÃ©nÃ©rez votre site, vous pouvez dÃ©finir un thÃ¨me en utilisant l'option `--theme`. Il est conseillÃ© de modifier votre fichier de configuration `config.toml` and dÃ©finir votre thÃ¨me par dÃ©faut. En passant, ajoutez les prÃ©requis Ã  l'utilisation de la fonctionnalitÃ© de recherche.

```toml
# Modifiez le thÃ¨me pour qu'il soit utilisÃ© par dÃ©faut Ã  chaque gÃ©nÃ©ration de site.
theme = "hugo-theme-learn"

# Pour la fonctionnalitÃ© de recherche
[outputs]
home = [ "HTML", "RSS", "JSON"]
```

## CrÃ©er votre premiÃ¨re page chapitre

Les *chapitres* sont des pages contenant d'autre pages filles. Elles ont un affichage spÃ©cial et contiennent habituellement juste un _nom_ de chapitre, le _titre_ et un _rÃ©sumÃ©_ de la section.

```
### Chapitre 1

# DÃ©marrage

DÃ©couvrez comment utiliser ce thÃ¨me Hugo et apprenez en les concepts
```

s'affiche comme

![Un chapitre](/en/basics/installation/images/chapter.png?classes=shadow&width=60pc)

**Hugo-theme-learn** fournit des archÃ©types pour crÃ©er des squelettes pour votre site. Commencez par crÃ©er votre premier chapitre avec la commande suivante:

```
hugo new --kind chapter basics/_index.md
```

En ouvrant le fichier gÃ©nÃ©rÃ©, vous devriez voir la propriÃ©tÃ© `chapter=true` en haut, paramÃ¨tre quit dÃ©finit que le page est un _chapitre_.

## CrÃ©er votre premiÃ¨re page

Puis, crÃ©ez votre premier page dans le chapitre prÃ©cÃ©dent. Pour ce faire, il existe deux possibilitÃ©s :

```
hugo new basics/first-content.md
hugo new basics/second-content/_index.md
```

N'hÃ©sitez pas Ã  Ã©diter ces fichiers en ajoutant des exemple de contenu et en remplaÃ§ant le paramÃ¨tre `title` au dÃ©but du fichier. 

## Lancer le site localement

Lancez la commande suivante :

```
hugo serve
```

Se rendre sur `http://localhost:1313`

Vous devriez voir trois choses:

1. Vous avez un menu **Basics** Ã  gauche, qui contient deux sous-menu avec des noms Ã©gal au paramÃ¨tre `title` des fichiers prÃ©cÃ©demment gÃ©nÃ©rÃ©s.
2. La page d'accueil vous explique comment la modifier. Suivez les instructions.
3. Avec la commande `hugo serve`, la page se rafraichit automatiquement Ã  chaque fois que vous sauvegardez. Super !

## GÃ©nÃ©rez le site

Quand votre site est prÃªt Ã  Ãªtre dÃ©ployÃ©, lancez la commande suivante:

```
hugo
```

Un dossier `public` a Ã©tÃ© gÃ©nÃ©rÃ©. Il contient tout le contenu statique et les ressources nÃ©cessaires pour votre site. Votre site peut maintenant Ãªtre dÃ©ployÃ© en utilisant n'importe quel serveur !

{{% notice note %}}
Ce site peut Ãªtre automatiquement publiÃ© et hÃ©bergÃ© avec [Netlify](https://www.netlify.com/) ([Plus d'infos](https://www.netlify.com/blog/2015/07/30/hosting-hugo-on-netlifyinsanely-fast-deploys/)). Sinon, vous pouvez utiliser les [Github pages](https://gohugo.io/hosting-and-deployment/hosting-on-github/)
{{% /notice %}}
