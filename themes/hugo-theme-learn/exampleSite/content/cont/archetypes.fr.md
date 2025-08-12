---
title: ArchÃ©types
weight: 10
---

En utilisant la commande: `hugo new [chemin vers nouveau contenu]`, vous pouvez crÃ©er un nouveau fichier avec la date et le title automatiquement initialisÃ©. MÃªme si c'est une fonctionnalitÃ© intÃ©ressante, elle reste limitÃ©e pour les auteurs actifs qui ont besoin de mieux : les [archetypes](https://gohugo.io/content/archetypes/).

Les archÃ©types sont des squelettes de pages prÃ©configurÃ©es avec un Front Matter par dÃ©faut. Merci de vous rÃ©fÃ©rer Ã  la documentation pour connaitre les diffÃ©rents types de page.

## Chapitre {#archetypes-chapter}

Pour crÃ©er un chapitre, lancez les commandes suivantes

```
hugo new --kind chapter <name>/_index.md
```

Cela crÃ©Ã©ra une page avec le Front Matter suivant:

```markdown
+++
title = "{{ replace .Name "-" " " | title }}"
date = {{ .Date }}
weight = 5
chapter = true
pre = "<b>X. </b>"
+++

### Chapter X

# Some Chapter title

Lorem Ipsum.
```

## DÃ©faut

Pour crÃ©er une page classique, lancer l'une des deux commandes suivantes

```
# Soit
hugo new <chapter>/<name>/_index.md
# Ou
hugo new <chapter>/<name>.md
```

Cela crÃ©Ã©ra une page avec le Front Matter suivant:

```markdown
+++
title = "{{ replace .Name "-" " " | title }}"
date =  {{ .Date }}
weight = 5
+++

Lorem Ipsum.
```
