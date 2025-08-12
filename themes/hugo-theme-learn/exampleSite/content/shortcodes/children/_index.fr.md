---
title : Children (Pages filles)
description : Liste les pages filles de la page
---

Utilisez le shortcode *children* pour lister les pages filles de la page et tous ses dÃ©scendants (pages filles de pages filles). Par dÃ©faut, le shortcode affiche des liens vers les pages filles.

## Utilisation

| ParamÃ¨tre | DÃ©faut | Description |
|:--|:--|:--|
| page | _current_ | SpÃ©cifie le nom de la page (nom de la section) Ã  afficher |
| style | "li" | Choisi le style Ã  utiliser pour afficher les descendants. Cela peut Ãªtre n'importe quel balise HTML |
| showhidden | "false" | Quand *true*, pages filles cachÃ©es dans le menu seront affichÃ©es quand mÃªme |
| description  | "false" | Permet d'inclure le texte de la description de la page sous chaque entrÃ© de la liste.<br/>quand aucune description existe pour la page, le shortcode prend les 70 premiers mots du contenu. [plus d'infos sur gohugo.io](https://gohugo.io/content/summaries/)  |
| depth | 1 | Nombre de descendants Ã  afficher. Par exemple, si la valeur est 2, le shortcode va afficher 2 niveaux de pages filels. <br/> **Astuce:** Utilisez 999 pour avoir tous les descendants|
| sort | <rien> | Tri les pages filles par<br><li><strong>Weight</strong> - Poids</li><li><strong>Name</strong> - Nom</li><li><strong>Identifier</strong> - Trier alphabÃ©tiquement par identifiant configurÃ© dans le front matter</li><li><strong>URL</strong> - URL</li> |

## DÃ©mo

	{{%/* children  */%}}

{{% children %}}

	{{%/* children description="true"   */%}}

{{%children description="true"   %}}

	{{%/* children depth="3" showhidden="true" */%}}

{{% children depth="3" showhidden="true" %}}

	{{%/* children style="h2" depth="3" description="true" */%}}

{{% children style="h2" depth="3" description="true" %}}

	{{%/* children style="div" depth="999" */%}}

{{% children style="div" depth="999" %}}






