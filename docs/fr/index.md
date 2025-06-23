# Tutoriel Copilot & Co

## Quid des assistants de code basé sur l'IA générative (Gen AI) ?

***Disclaimer*** : *Ce tutoriel a pour objectif de présenter quelques cas d'usage des assistants de code basés sur des modèles d'IA génératives. Il vise également à sensibiliser aux avantages de ces outils, tels que l'amélioration de la productivité et l'optimisation des pratiques de développement, tout en mettant en lumière leurs limites.*

*Initialement conçu pour des étudiants bénéficiant de l'offre [GitHub Education][githubEducationLink], GitHub Copilot a été choisi pour illustrer ces cas d'usage. Cependant, il est tout à fait possible de suivre ce tutoriel en utilisant d'autres assistants de code, comme [Codeium][codeiumLink], [Cursor][cursorLink], [Supermaven](https://supermaven.com/) ou [Tabnine][tabnineLink],... qui offrent des services similaires. Le terme "**assistant de code**" sera donc privilégié autant que possible.*

*Ce tutoriel a été rédigé à l'automne 2024 pour permettre aux étudiants de deuxième année de BUT Informatique d'expérimenter les assistants de code, à un moment où ces outils basés sur l'IA générative étaient en plein essor. Depuis, ces assistants ont connu de rapides évolutions et génèrent aujourd'hui moins d'hallucinations qu'à leurs débuts, c'est-à-dire au moment de la rédaction de ce tutoriel.*

Dans ce tutoriel, nous verrez comment :

* **[1. Installation de l'assistant de code Github Copilot][Installation]**
* **[2. Prise en main de l'assistant de code : premiers pas sur un exemple simple][contenu_partie_2]**
* **[3. Aider à la mise en place de nouvelles règles métiers sur un projet existant simple][contenu_partie_3]**
* **[4. Quid d'un assistant de code pour la reprise d'un projet complexe existant (legacy code)][contenu_partie_4]**

Et vous trouverez [quelques liens utiles][contenu_liens] consultés pendant la rédaction de ce tutoriel.

Ce tutoriel est accompagné d'un formulaire. N'hésitez pas à compléter ce **formulaire accessible [ici](https://forms.gle/YquLZ7CMsmmgvwHUA)** en même temps que vous réalisez le tutoriel.

Pour commencer le tutoriel, c'est par [là][Installation] si vous avez besoin d'installer Github Copilot dans votre IDE préféré.  
Sinon vous pouvez commencer directement [ici][contenu_partie_2] pour prendre en main et faire vos premiers pas avec votre assistant de code préféré.

## A propos de l'approche pédagogique

Ce tutoriel a été conçu pour aider les étudiants à développer à la fois leurs compétences techniques et leur esprit critique dans l'usage d'un assistant de code basé sur l'IA. Il permet d'explorer, de réfléchir et de progresser avec l'IA.

Pour développer leur esprit critique, cette approche pédagogique repose sur un processus d'apprentissage en trois étapes, itératif et incrémental :

1. **Expérimenter**  
*Explorer et tester l'assistant en suivant le tutoriel. Observer son comportement, explorer ses capacités et identifier ses limites.*  
L'étudiant se confronte à l'outil en observant son comportement et en découvrant ses forces et ses faiblesses par la **pratique**.  
Certains scénarios ont été spécialement conçus pour mettre en évidence ses limites, notamment en cherchant à provoquer des **hallucinations** (réponses incorrectes ou trompeuses générées par les modèles de langage au cœur de l'IA générative.). Compte tenu du caractère probabiliste de l'outil, ces hallucinations peuvent ne pas apparaître systématiquement c'est pourquoi elles sont explicitement expliquées dans le tutoriel.

2. **Analyser** *la réponse générée par l'IA*  
*Prendre du recul grâce à un questionnaire réflexif. Réfléchir à ce qui a bien fonctionné, à ce qui a posé problème, et pourquoi. S'appuyer sur sa propre expertise pour interpréter les suggestions de l'assistant.*  
Vient ensuite un temps de ***réflexion guidée***, appuyée par un ***questionnaire***, des explications fournies dans le tutoriel et la mobilisation de sa propre ***expertise***. L'objectif ici est de passer d'une observation intuitive à une compréhension critique du fonctionnement (et des erreurs) de l'IA.

3. **Ajuster** *la suggestion de l'IA*  
A*ffiner les prompts, corriger les erreurs et prendre des décisions éclairées.*  
Enfin, les étudiants sont invités à corriger, adapter, affiner les suggestions de l'IA en exerçant leur propre ***libre-arbitre***. C'est ici que se joue l'***autonomisation*** face à l'outil en restant pleinement acteur ou actrice de leur apprentissage.

Trois principes guident cette démarche : une **intégration progressive de l'outil**, une **validation critique du code produit**, et une **autonomie** construite à travers l'ajustement des suggestions, la réflexion sur les décisions prises, et l'apprentissage d'un usage raisonné et efficace des outils d'IA.

## Papier de recherche

Cette expérience pédagogique a fait l'objet d'un article présenté à la conférence [ITiCSE 2025](https://iticse.acm.org/2025) :  
**[Developing Critical Thinking with AI Coding Assistants: An Educational Experience Focusing on Testing and Legacy Code](https://dl.acm.org/doi/10.1145/3724363.3729050)**.

## On en discute ?

Pour les discussions, c'est par [là](https://github.com/iblasquez/tuto-copilot-genai/issues)  
Pour les propositions de contenu, de modification par [ici](https://github.com/iblasquez/tuto-copilot-genai/pulls)  

## Licence

Ce document est placé sous licence CC BY-NC-SA :  
[Creative Commons
Attribution - Pas d'Utilisation Commerciale - Partage dans les Mêmes Conditions](https://creativecommons.org/licenses/by-nc-sa/4.0/)

En savoir plus sur [les licences Creative Commons](https://creativecommons.org/licenses/?lang=fr-FR) ...

Toutefois, toute personne enseignant à l'Université de Limoges souhaitant utiliser ces documents doit demander une autorisation préalable :smile:

[Installation]: 1_Installation.md
[contenu_partie_2]: 2_PriseEnMainAssistant.md
[contenu_partie_3]: 3_ProjetExistantSimple.md
[contenu_partie_4]: 4_ProjetExistantComplexe.md
[contenu_liens]: Liens.md

<!-- https://www.jdbonjour.ch/cours/markdown-pandoc/ >
https://www.statpower.net/Content/310/R%20Stuff/SampleMarkdown.html -->

[tabnineLink]: https://www.tabnine.com
[codeiumLink]: https://codeium.com
[cursorLink]: https://www.cursor.com
[githubEducationLink]: https://github.com/education
