---
title: Attachments (PiÃ¨ces jointes)
description : "The Attachments shortcode displays a list of files attached to a page."
---

Le shortcode *Attachments* affiche une liste de piÃ¨ces jointes d'une page.

{{% attachments /%}}

## Utilisation

Le shortcode affiche la liste de fichiers trouvÃ©s dans un **dossier spÃ©cifique**
A l'heure actuelle, il supporte deux implÃ©mentations

1. Si votre page est un fichier Markdown, les piÃ¨ces jointes doivent Ãªtre placÃ©e dans un **dossier** nommÃ© comme le nom de la page et suffixÃ© par **.files**.

    > * content
    >   * _index.md
    >   * page.files
    >      * attachment.pdf
    >   * page.md

2. Si votre page est un **dossier**, les piÃ¨ces jointes doivent Ãªtre placÃ©es dans un dossier fils **'files'**.

    > * content
    >   * _index.md
    >   * page
    >      * index.md
    >      * files
    >          * attachment.pdf

Attention, si votre site est multi-langue, vous devrez avec autant de dossier qu'il y a de langues.

C'est tout !

### ParamÃ¨tres

| ParamÃ¨tre | DÃ©faut | Description |
|:--|:--|:--|
| title | "PiÃ¨ces jointes" | Titre de la liste  |
| style | "" | Choisir entre "orange", "grey", "blue" et "green" pour un style plus sympa |
| pattern | ".*" | Une expression rÃ©guliÃ¨re, utilisÃ©e pour filtrer les piÃ¨ces jointes par leur nom de fichier. <br/><br/>Le paramÃ¨tre **pattern** doit Ãªtre une [expression rÃ©guliÃ¨re](https://en.wikipedia.org/wiki/Regular_expression).

Par exemple:

* Pour trouver les fichiers avec le suffixe 'jpg', utilisez **.*jpg** (pas *.jpg).
* Pour trouver les fichiers avec les suffixe 'jpg' ou 'png', utilisez **.*(jpg|png)**

### Exemples

#### Lister les piÃ¨ces jointes de type pdf ou mp4


    {{%/*attachments title="Fichiers associÃ©s" pattern=".*(pdf|mp4)"/*/%}}

s'affiche comme

{{%attachments title="Fichiers associÃ©s" pattern=".*(pdf|mp4)"/%}}

#### Modifier le style

    {{%/*attachments style="orange" /*/%}}

s'affiche comme

{{% attachments style="orange" /%}}


    {{%/*attachments style="grey" /*/%}}

s'affiche comme

{{% attachments style="grey" /%}}

    {{%/*attachments style="blue" /*/%}}

s'affiche comme

{{% attachments style="blue" /%}}
    
    {{%/*attachments style="green" /*/%}}

s'affiche comme

{{% attachments style="green" /%}}
