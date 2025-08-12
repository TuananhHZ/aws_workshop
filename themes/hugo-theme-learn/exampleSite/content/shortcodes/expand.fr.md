---
title : Expand
description : "Affiche une section de texte qui se plie et se dÃ©plie"
---

Le shortcode *Expand* affiche une section de texte qui se plie et se dÃ©plie.
Ci-dessous un exemple.

{{%expand%}}
Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
{{%/expand%}}


## Utilisation


Ce shortcode prends exactement un paramÃ¨tre optionel pour dÃ©finir le texte Ã  cÃ´tÃ© de l'icone. (valeur par dÃ©faut est "DÃ©roulez-moi...")

	{{%/*expand "Est-ce que ce thÃ¨me envoie du pÃ¢tÃ© ?" */%}}Oui !.{{%/* /expand*/%}}

{{%expand "Est-ce que ce thÃ¨me envoie du pÃ¢tÃ© ?" %}}Oui !{{% /expand%}}

# Demo

	{{%/*expand*/%}}
    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
	tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
	quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
	consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
	cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
	proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
    {{%/* /expand*/%}}


{{%expand%}}Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
proident, sunt in culpa qui officia deserunt mollit anim id est laborum.{{% /expand%}}
