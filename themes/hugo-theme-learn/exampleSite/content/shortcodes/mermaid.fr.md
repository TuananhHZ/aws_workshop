---
title : "Mermaid"
description : "GÃ©nÃ©ration de diagrammes Ã  partir de texte, dans le mÃªme style que Markdown"
---

[Mermaid](https://mermaidjs.github.io/) est une bibliothÃ¨que Javascript qui permet de gÃ©nÃ©rer des diagrammes (sÃ©quence, Ã©tat, gantt, etc.) Ã  partir de texte, dans le mÃªme style que Markdown.

InsÃ©rer votre code Mermaid dans un shortcode `mermaid` et c'est tout.

## Flowchart example
	{{</*mermaid align="left"*/>}}
	graph LR;
		A[Bords droits] -->|Lien texte| B(Bords arondis)
    	B --> C{DÃ©cision}
    	C -->|Un| D[RÃ©sultat un]
    	C -->|Deux| E[RÃ©sultat deux]
    {{</* /mermaid */>}}

renders as

{{<mermaid align="left">}}
graph LR;
	A[Bords droits] -->|Lien texte| B(Bords arondis)
	B --> C{DÃ©cision}
	C -->|Un| D[RÃ©sultat un]
	C -->|Deux| E[RÃ©sultat deux]
{{< /mermaid >}}

or you can use this alternative syntax:

<pre>
```mermaid
graph LR;
	A[Bords droits] -->|Lien texte| B(Bords arondis)
	B --> C{DÃ©cision}
	C -->|Un| D[RÃ©sultat un]
	C -->|Deux| E[RÃ©sultat deux]
```
</pre>

renders as

```mermaid
graph LR;
	A[Bords droits] -->|Lien texte| B(Bords arondis)
	B --> C{DÃ©cision}
	C -->|Un| D[RÃ©sultat un]
	C -->|Deux| E[RÃ©sultat deux]
```

## Sequence example

	{{</*mermaid*/>}}
	sequenceDiagram
	    participant Alice
	    participant Bob
	    Alice->>John: Salut John, comment vas-tu?
	    loop VÃ©rification
	        John->John: Se bat contre l'hyponcodrie.
	    end
	    Note right of John: Les pensÃ©es rationnelles<br/>prÃ©dominent...
	    John-->Alice: Super!
	    John->Bob: Et toi?
	    Bob-->John: Au top!
	{{</* /mermaid */>}}

renders as

{{<mermaid>}}
sequenceDiagram
	participant Alice
	participant Bob
	Alice->>John: Salut John, comment vas-tu?
	loop VÃ©rification
		John->John: Se bat contre l'hyponcodrie.
	end
	Note right of John: Les pensÃ©es rationnelles<br/>prÃ©dominent...
	John-->Alice: Super!
	John->Bob: Et toi?
	Bob-->John: Au top!
{{< /mermaid >}}

or you can use this alternative syntax:

<pre>
```mermaid
sequenceDiagram
	participant Alice
	participant Bob
	Alice->>John: Salut John, comment vas-tu?
	loop VÃ©rification
		John->John: Se bat contre l'hyponcodrie.
	end
	Note right of John: Les pensÃ©es rationnelles<br/>prÃ©dominent...
	John-->Alice: Super!
	John->Bob: Et toi?
	Bob-->John: Au top!
```
</pre>

renders as

```mermaid
sequenceDiagram
	participant Alice
	participant Bob
	Alice->>John: Salut John, comment vas-tu?
	loop VÃ©rification
		John->John: Se bat contre l'hyponcodrie.
	end
	Note right of John: Les pensÃ©es rationnelles<br/>prÃ©dominent...
	John-->Alice: Super!
	John->Bob: Et toi?
	Bob-->John: Au top!
```

## GANTT Example

	{{</*mermaid*/>}}
	gantt
	        dateFormat  YYYY-MM-DD
	        title Ajout de la fonctionnalitÃ© de GANTT Ã  Mermaid
	        section Une section
	        TÃ¢che complÃ©tÃ©e            :done,    des1, 2014-01-06,2014-01-08
	        TÃ¢che en cours             :active,  des2, 2014-01-09, 3d
	        Future tÃ¢che               :         des3, after des2, 5d
	        Future tÃ¢che 2             :         des4, after des3, 5d
	        section TÃ¢ches critiques
	        TÃ¢che complÃ©tÃ©e dans le chemin critique :crit, done, 2014-01-06,24h
	        ImplÃ©menter le parser et jison          :crit, done, after des1, 2d
	        CrÃ©er des tests pour le parser          :crit, active, 3d
	        Future tÃ¢che dans le chemin critique    :crit, 5d
	        CrÃ©er des tests pour le renderer        :2d
	        Ajout Ã  Mermaid                      	:1d
	{{</* /mermaid */>}}


renders as

{{<mermaid>}}
gantt
		dateFormat  YYYY-MM-DD
		title Ajout de la fonctionnalitÃ© de GANTT Ã  Mermaid
		section Une section
		TÃ¢che complÃ©tÃ©e            :done,    des1, 2014-01-06,2014-01-08
		TÃ¢che en cours             :active,  des2, 2014-01-09, 3d
		Future tÃ¢che               :         des3, after des2, 5d
		Future tÃ¢che 2             :         des4, after des3, 5d
		section TÃ¢ches critiques
		TÃ¢che complÃ©tÃ©e dans le chemin critique :crit, done, 2014-01-06,24h
		ImplÃ©menter le parser et jison          :crit, done, after des1, 2d
		CrÃ©er des tests pour le parser             :crit, active, 3d
		Future tÃ¢che dans le chemin critique        :crit, 5d
		CrÃ©er des tests pour le renderer           :2d
		Ajout Ã  Mermaid                      :1d
{{</mermaid>}}


or you can use this alternative syntax:

<pre>
```mermaid
gantt
		dateFormat  YYYY-MM-DD
		title Ajout de la fonctionnalitÃ© de GANTT Ã  Mermaid
		section Une section
		TÃ¢che complÃ©tÃ©e            :done,    des1, 2014-01-06,2014-01-08
		TÃ¢che en cours             :active,  des2, 2014-01-09, 3d
		Future tÃ¢che               :         des3, after des2, 5d
		Future tÃ¢che 2             :         des4, after des3, 5d
		section TÃ¢ches critiques
		TÃ¢che complÃ©tÃ©e dans le chemin critique :crit, done, 2014-01-06,24h
		ImplÃ©menter le parser et jison          :crit, done, after des1, 2d
		CrÃ©er des tests pour le parser             :crit, active, 3d
		Future tÃ¢che dans le chemin critique        :crit, 5d
		CrÃ©er des tests pour le renderer           :2d
		Ajout Ã  Mermaid                      :1d
```
</pre>

renders as

```mermaid
gantt
		dateFormat  YYYY-MM-DD
		title Ajout de la fonctionnalitÃ© de GANTT Ã  Mermaid
		section Une section
		TÃ¢che complÃ©tÃ©e            :done,    des1, 2014-01-06,2014-01-08
		TÃ¢che en cours             :active,  des2, 2014-01-09, 3d
		Future tÃ¢che               :         des3, after des2, 5d
		Future tÃ¢che 2             :         des4, after des3, 5d
		section TÃ¢ches critiques
		TÃ¢che complÃ©tÃ©e dans le chemin critique :crit, done, 2014-01-06,24h
		ImplÃ©menter le parser et jison          :crit, done, after des1, 2d
		CrÃ©er des tests pour le parser             :crit, active, 3d
		Future tÃ¢che dans le chemin critique        :crit, 5d
		CrÃ©er des tests pour le renderer           :2d
		Ajout Ã  Mermaid                      :1d
```

### Class example

<pre>
```mermaid
classDiagram
  Class01 <|-- AveryLongClass : Cool
  Class03 *-- Class04
  Class05 o-- Class06
  Class07 .. Class08
  Class09 --> C2 : Where am i?
  Class09 --* C3
  Class09 --|> Class07
  Class07 : equals()
  Class07 : Object[] elementData
  Class01 : size()
  Class01 : int chimp
  Class01 : int gorilla
  Class08 <--> C2: Cool label
```
</pre>

renders as

```mermaid
classDiagram
  Class01 <|-- AveryLongClass : Cool
  Class03 *-- Class04
  Class05 o-- Class06
  Class07 .. Class08
  Class09 --> C2 : Where am i?
  Class09 --* C3
  Class09 --|> Class07
  Class07 : equals()
  Class07 : Object[] elementData
  Class01 : size()
  Class01 : int chimp
  Class01 : int gorilla
  Class08 <--> C2: Cool label
```

### Git example

<pre>
```mermaid
gitGraph:
options
{
  "nodeSpacing": 150,
  "nodeRadius": 10
}
end
  commit
  branch newbranch
  checkout newbranch
  commit
  commit
  checkout master
  commit
  commit
  merge newbranch
```
</pre>

renders as

```mermaid
gitGraph:
options
{
  "nodeSpacing": 150,
  "nodeRadius": 10
}
end
  commit
  branch newbranch
  checkout newbranch
  commit
  commit
  checkout master
  commit
  commit
  merge newbranch
```
