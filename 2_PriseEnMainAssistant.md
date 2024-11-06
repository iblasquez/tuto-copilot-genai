# 2. Prise en main de l'assistant de code : premiers pas sur un exemple simple

---

- [Générer des suggestions de code à partir de commentaires](#générer-des-suggestions-de-code-à-partir-de-commentaires-qui-décrivent-un-comportement-donné)
- [Générer le code de tests (unitaires)](#générer-le-code-de-tests-unitaires)
- [Expliquer comment fonctionne le code (`/explain`)](#expliquer-comment-fonctionne-le-code-explain)
- [Quelques mots sur la notion de prompt](#quelques-mots-sur-la-notion-de-prompt)
- [Les commandes slash de Copilot : une aide au prompting pour des tâches/actions récurrentes](#les-commandes-slash-de-copilot--une-aide-au-prompting-pour-des-tâchesactions-récurrentes)
- [Faciliter la résolution de problèmes dans le code : fixer, refactorer, améliorer](#faciliter-la-résolution-de-problèmes-dans-le-code--fixer-refactorer-améliorer)
  - [Fixer : `/fix`](#fixer--fix)
  - [Refactorer un bout de code](#refactorer-un-bout-de-code)
  - [Demander comment améliorer la qualité du code](#demander-comment-améliorer-la-qualité-du-code)
- [Générer facilement de la documentation : `/doc`](#générer-facilement-de-la-documentation--doc)
- [Approfondir un sujet en lien avec le développement logiciel](#approfondir-un-sujet-en-lien-avec-le-développement-logiciel)
- [Mais Copilot n'est qu'un assistant autour du développement logiciel](#mais-copilot-nest-quun-assistant-autour-du-développement-logiciel)
- [Guider pas à pas la prise en main de nouveau(x) outil(s)](#guider-pas-à-pas-la-prise-en-main-de-nouveaux-outils)
- [Améliorer la pertinence des réponses de Copilot en ciblant le contexte du prompt avec des références (agents de conversation)](#améliorer-la-pertinence-des-réponses-de-copilot-en-ciblant-le-contexte-du-prompt-avec-des-références-agents-de-conversation)

---

Rien de tel qu'un exemple simple pour prendre en main un nouvel outil.  
Dans votre IDE préféré, dans un projet Java que vous appellerez **maths**, créez une classe `Calculator` contenant l'implémentation suivante :

```java
public class Calculator {
    public int add(int a, int b) {
        return a + b;
    }

    public int subtract(int a, int b) {
        return a - b;
    }

    public int multiply(int a, int b) {
        return a * b;
    }

    public int divide(int a, int b) {
        if (b == 0) {
            throw new IllegalArgumentException("Cannot divide by zero");
        }
        return a / b;
    }
}
```

## Générer des suggestions de code à partir de commentaires (qui décrivent un comportement donné)

- Placez votre curseur à la fin de la classe (sur la ligne juste avant l'accolade fermante `}`).
- **Écrivez un commentaire** qui montre **l'intention du code** que vous cherchez à implémenter, comme par exemple :  
  `//Method to calculate the square root`  
  Puis appuyez sur la touche **Entrée** et observez...  

- **L'assistant de code** suggère une implémentation pour le comportement décrit dans le commentaire.

- Si cette implémentation répond bien à vos besoins et que vous souhaitez **insérer dans votre éditeur *tout* le code suggéré par votre assistant**, appuyez sur la touche **Tabulation** de votre clavier.

- Écrivez un nouveau commentaire pour une nouvelle méthode, par exemple :  
  `//Method to calculate the logarithm`  
  Appuyez sur **Entrée** pour visualiser le code généré par votre assistant pour répondre à ce comportement.

- Vous n'êtes pas obligé de valider totalement la suggestion de l'assistant, vous pouvez **insérer partiellement le code proposé par l'assistant** :
  - **Ctrl+Flèche Droite** permet d'**insérer un seul mot à la fois**.
  - **Ctrl+Alt+Flèche Droite** permet d'**insérer une seule ligne à la fois**.

- Placez-vous sur une nouvelle ligne et attendez. Sans commentaire (c.-à-d. sans demande explicite), votre assistant vous propose quand même des suggestions de code sur des méthodes qui pourraient venir enrichir, selon lui, le comportement de votre classe. A vous de décider, selon vos besoins, s'il est pertinent ou pas d'ajouter le code suggéré/généré.

### À retenir

- Pour chaque tâche, commencez par écrire un commentaire décrivant ce que vous souhaitez faire, puis laissez l'assistant de code vous suggérer une implémentation. N'oubliez pas que l'assistant de code est un outil d'assistance et que vous devez toujours vérifier, comprendre et éventuellement ajuster le code qu'il génère.
- Si la proposition de votre assistant ne vous convient pas, appuyez simplement sur **Entrée** pour écrire votre propre code.

## Générer le code de tests (unitaires)

- Avec l'aide de votre IDE, créez maintenant, au bon endroit de votre projet, une classe `CalculatorTest` qui regroupera les tests unitaires relatifs à la classe `Calculator`.

- Placez-vous dans cette nouvelle classe (vide : faites en sorte que cette classe ne contienne aucun test pour le moment)  et attendez la suggestion de votre assistant.

- **Votre assistant** devrait vous suggérer un jeu complet de tests unitaires pour chacune des méthodes de la classe. Appuyez sur **Tabulation** pour insérer le code suggéré dans cette classe.

- Lancez les tests pour vérifier qu'ils passent bien tous et consultez la couverture de code.

- Si votre assistant ne vous fait aucune suggestion, vous pouvez procéder comme précédemment et écrire un commentaire décrivant le comportement à tester. Si, par exemple, vous souhaitez disposer d'une méthode de test pour le cas de la division par zéro :
  - Ecrivez comme commentaire : `//test divide by zero`  
  - L'assistant commencera par proposer l'annotation `@Test` qu'il faut valider avec **Tabulation**. Appuyez ensuite sur **Entrée** pour que l'assistant continue ses suggestions.  
  - L'assistant propose alors l'implémentation de la méthode de test que vous pouvez choisir de **valider** en appuyant sur **Tabulation** ou de **refuser** en appuyant sur **Entrée**, vous permettant ainsi de reprendre la main dans votre IDE.

## Expliquer comment fonctionne le code (`/explain`)

- Sélectionnez dans la classe `Calculator` tout le **code de la méthode `divide`**.
- Une fois ce code sélectionné (surligné), **ouvrez le chat de votre assistant**.
Pour ouvrir le chat de copilot, faites un clic droit, recherchez quelque chose comme **(Github)Copilot** puis sélectionnez quelque chose comme **OpenChatPanel** : le chat de l'assistant devrait alors **s'ouvrir sur le côté (droit) de votre IDE**.
Dans certains IDE, il est également possible d'ouvrir directement le chat au milieu du code (InLine Chat). Mais pour ce tutoriel, nous vous conseillons d'utiliser le chat classique.

- Le chat de l'assistant fonctionne comme un chat IA classique. Une fois le code sélectionné, il suffit de poser une question, par exemple: **`Comment fonctionne ce code ?`**
  L'assistant vous expliquera alors comment fonctionne ce morceau de code.

- Dans le cadre du développement logiciel, les développeurs se posent souvent la question : **Comment fonctionne ce code ?**. Pour faciliter l'écriture de cette question répétitive dans le chat, **Copilot** propose un raccourci dédié : la commande  **`/explain`**.
  Assurez-vous que le code de la méthode `divide` est toujours sélectionné, puis tapez `/explain` dans le chat et appuyez sur **Entrée**. Comme précédemment, Copilot fournira une description détaillée de ce que fait le code.

## Quelques mots sur la notion de prompt

Il est maintenant temps d'introduire la notion de prompt.
Dans le domaine de l'intelligence artificielle (IA), un **prompt** est une instruction ou un ensemble de données que vous fournissez à un système d'IA pour qu'il génère une réponse. En d'autres termes, c'est la manière dont vous interagissez/dialoguez avec votre assistant de code.  
Les prompts peuvent être des phrases courtes, des questions ou des mots-clés. La pertinence et la qualité des réponses fournies par l'assistant de code (ou tout autre agent conversationnel IA) dépendent directement de la qualité de vos prompts, c'est-à-dire de la clarté et de la précision des informations que vous fournissez.

## Les commandes slash de Copilot : une aide au prompting pour des tâches/actions récurrentes

&#8594; Copilot propose des raccourcis, appelés **commandes slash** (ou slash commands), qui permettent d'exécuter un certain nombre de tâches répétitives et typiques du développement logiciel. En tapant une **barre oblique (slash) (`/`)** dans le chat, Copilot vous suggère une liste de commandes pour interagir rapidement avec lui.  
Nous venons d'utiliser `/explain`, nous explorerons d'autres commandes slash au cours du tutoriel.

Le tableau ci-dessous donne **la liste des commandes slash** proposées actuellement dans Copilot :

| Commande slash  | Description |
|-----------------|-------------|
| `/explain`      | Explain how the code works |
| `/feedback`     | Steps to provide feedback |
| `/fix`          | Fix problems and compile errors |
| `/help`         | Get help on how to use Copilot chat |
| `/tests`        | Generate unit tests |
| `/doc`          | Document current selection of code |
| `/simplify`     | Simplify the code |

&#8594; Par défaut, le chat de Copilot se réfère au **fichier ouvert** ou au **code sélectionné**.
Cependant, vous pouvez indiquer explicitement le fichier auquel vous souhaitez faire référence dans le chat. Pour cela, faites un clic droit sur le fichier concerné, sélectionnez **GitHub Copilot**, puis cliquez sur **Reference File in Chat**. Le fichier sera alors explicitement référencé dans le chat.

**Disclaimer** : *Dans les cas d'usage que vous allez explorer dans la suite de ce tutoriel les commandes slash vont souvent être utilisées comme prompt pour dialoguer de manière succincte, mais précise avec votre assistant.*

***Si vous utilisez un autre assistant de code, autre que Copilot,** votre assistant proposera surement un équivalent à la commande slash de Copilot. Si ce n'est pas le cas, à chaque fois qu'une commande slash sera utilisée dans la suite de ce tutoriel, **veuillez écrire comme prompt la phrase complète donnée comme description dans le tableau précédent** qui décrit en détail la tâche demandée à l'assistant &#8230;ou bien essayez de faire apprendre ce raccourci à votre assistant de code préféré &#128522;*

## Faciliter la résolution de problèmes dans le code : fixer, refactorer, améliorer

### Fixer : `/fix`

Si le fichier **actif** contient une erreur, utilisez la commande slash `/fix` pour demander à Copilot comment corriger l'erreur.

- Par exemple, placez-vous dans la classe `CalculatorTest` et effacez tous les **`import`**.
- Des erreurs de compilation apparaissent alors dans ce fichier.
- Rendez-vous dans le chat et tapez la commande `/fix`.  
  L'assistant vous indiquera alors comment résoudre ces erreurs de compilation.

Avant de continuer, remettez les **`import`** et assurez-vous que le code compile et que les tests passent.

> **Rappel :** `/fix` est un alias qui permet d'éviter d'écrire entièrement "Fix problems and compile errors".

### Refactorer un bout de code

- Revenez dans la classe `Calculator` et sélectionnez (surlignez) tout le code de la méthode `divide`, qui fera office de code à refactorer.

- En (re)lisant ce code, voua avez détectez un **smell code** au niveau du **nommage** des paramètres de la méthode, demandez de l'aide à l'assistant en tapant dans le chat : `use better names for parameters`.

- L'assistant vous suggère alors un nouveau bout de code avec des noms plus explicites qui corrige le smell code précédent comme vous le souhaitiez.

- Amenez votre curseur dans le coin **en haut à droite du cadre qui contient le code proposé par l'assistant** pour voir apparaître les deux icônes suivantes (l'ordre des icônes peut varier selon les IDE). Quoi qu'il en soit :
  - Une icône permet de copier le code proposé
  - Une icône permet d'insérer directement le code dans l'éditeur (celle avec la flèche).

- Cliquez sur l'**icône qui permet d'insérer directement le code dans l'éditeur** (flèche).

- Il ne reste plus qu'à constater que le bout de code initialement surligné a bien été remplacé dans la classe `Calculator` par le code proposé par l'assistant.

- Et comme pour tout refactoring, avant de continuer, il est nécessaire de relancer les tests pour vérifier qu'ils passent toujours et que le comportement n'a pas changé.

Nous avons vu précédemment qu'**écrire un commentaire** directement dans le code pour décrire le comportement souhaité est une **approche pratique pour *"*interpeller*"* l'assistant de code et obtenir des suggestions directement à l'endroit approprié**.
Toutefois, une fois la suggestion de code validée, le commentaire reste, comme c'est le cas actuellement dans la classe `Calculator` pour les méthodes  `squareRoot` et  `logarithm` générées précédemment par l'assistant.

Or, garder **un commentaire expliquant ce que fait le code est considéré comme un code smell** (mauvaise pratique), surtout si le nom des méthodes est déjà explicite. Un petit refactoring s'impose pour éliminer cette *mauvaise odeur* du code.

- Pour supprimer ces commentaires, sélectionnez le code des deux méthodes, y compris leurs commentaires et demandez à l'assistant d'éliminer ces commentaires en tapant dans le chat :
`supprimer les commentaires`
(ou `remove comments` si vous préférez lui parler en anglais)

- Ensuite, cliquez sur l'icône avec la flèche pour accepter la suggestion de l'assistant et insérer directement le code corrigé par l'assistant dans le fichier source, remplaçant ainsi la portion de code précédemment sélectionnée.

**Remarque :** Vous auriez également pu sélectionner tout le code de la classe. Cette petite manipulation vise à montrer que le refactoring (remaniement de code) par l'assistant n'est pas limité à une méthode unique, mais peut s'appliquer sur un bout de code plus important 😉

- Et comme pour tout refactoring, n'oubliez pas de terminer en relançant les tests.

### Demander comment améliorer la qualité du code

Bien sûr, il est toujours possible d'utiliser le chat de l'assistant de code comme un chat d'une IA classique, en formulant des requêtes variées et plus ou moins précises pour améliorer la qualité du code.

- Par exemple, tapez dans le chat une question du type :
`comment améliorer la qualité de ce code ?`
dans la langue de votre choix (français ou anglais) :  `how would you improve this code ?`

Pour l'instant, contentez-vous simplement de dialoguer avec votre assistant de code.
Peut-être que la réponse qu'il vous fournira satisfera votre curiosité  
Toutefois, si vous souhaitez une réponse plus détaillée ou orientée vers un objectif bien précis, vous pouvez bien sûr poursuivre la conversation avec l'assistant afin d'affiner ses réponses/suggestions.

*Lors du prompt précédent autour de la qualité de code, votre assistant vous a peut-être indiqué que  **«Utilisez des commentaires Javadoc pour documenter les méthodes publiques.»** pouvait être considéré, **selon lui**, comme un **critère de qualité**.*

## Générer facilement de la documentation : `/doc`

Les **commentaires Javadoc** sont différents des **simples commentaires** dans le code.
Pour en savoir plus (et vous convaincre cette différence), demandez de l'aide à votre assistant de code en lui demandant de répondre à la question suivante :
`Quelle est la différence entre des commentaires javadoc et de simples commentaires ?`

Votre assistant vous expliquera probablement que **les commentaires Javadoc sont utilisés pour générer de la documentation d'une API.**

Par exemple, la **Javadoc du SDK de Java** (disponible sur le site Oracle : <https://docs.oracle.com>) est générée à partir des commentaires Javadoc présents dans les classes Java du SDK, que vous utilisez dans vos programmes. Ainsi, si votre classe Java est destinée à devenir une API, utilisable par des développeurs externes, les commentaires Javadoc deviennent, dans ce cas d'usage, un critère important de qualité.

Mais tout développeur sait qu'écrire de la documentation est une tâche fastidieuse.
Heureusement, l'assistant de code peut vous aider à automatiser cette tâche et améliorer votre productivité grâce à la commande slash
 `/doc`.

- Revenez sur la classe `Calculator` et tapez dans le chat : `/doc`
(qui correspond en réalité à la phrase complète `Document current selection of code`)

- L'assistant de code vous proposera alors **le code de la classe documenté avec les commentaires Javadoc** qu'il vient de générer

- Sélectionnez tout le code de la classe `Calculator` et cliquez sur l'icône d'insertion de code (avec la flèche) pour remplacer le code existant par cle code documenté.

- Avant de continuer, relancez bien sûr les tests pour vérifier qu'ils continuent de passer (et que l'assistant de code n'a pas modifié le comportement de votre code, mais s'est bien juste contenté d'ajouter des commentaires)

*Au fil de vos échanges avec l'assistant, vous aurez sans doute remarqué que **ce dernier ne se contente pas de répondre à vos demandes. Il vous suggère également une question (en lien avec votre demande) pour vous aider à affiner votre prompt ou à approfondir le sujet sur lequel vous interagissez.***

## Approfondir un sujet en lien avec le développement logiciel

Suite à la commande `/doc`, votre assistant de code vous a généré le code documenté demandé.  
Si vous consultez attentivement le chat, vous remarquerez probablement qu'**il vous a aussi proposé une question pour approfondir vos actions ou vos connaissances autour de la documentation**.  
Selon vos besoins ou votre curiosité, vous êtes libre de cliquer sur la question suggérée ou de l'ignorer.

Dans cette partie du tutoriel, il est temps **d'explorer ces questions suggérées** par votre assistant et d'en tirer parti **pour en apprendre davantage sur la documentation dans un projet**.

- Votre assistant de code vous suggère peut-être la question suivante :
`What other documentation styles can be used for Java code?`
Si ce n'est pas le cas, choisissez la question qui vous est proposée ou tapez directement cette question dans le chat.

- Vous pouvez ensuite poursuivre avec une question comme (suggérée ou tapée) :
`What are some best practices for writing documentation in Java?`

- Et pour terminer :
`What are some common mistakes to avoid when writing documentation in Java?`

Pour des recherches simples, ces échanges permettent d'explorer directement les connaissances de l'assistant dans votre IDE sans avoir besoin de consulter des ressources externes.

## Mais Copilot n'est qu'un assistant autour du développement logiciel

Comme tout modèle de langage, les assistants de code (comme Copilot) ont été entraînés sur un ensemble de données spécifiques. Il est important de garder à l'esprit que l'assistant de code que vous utilisez dans ce tutoriel, intégré à votre IDE, est **spécifiquement conçu pour le développement logiciel et a donc été entraîné sur des connaissances relatives à ce domaine**.

Ainsi, le chat de votre assistant de code ne remplacera pas celui d'un modèle de langage plus généraliste, tel que ChatGPT, bien que les deux soient basés sur OpenAI.

- Pour vous en convaincre, posez la question suivante à votre assistant de code :  
`What is the best documentation for visiting the city of Limoges?`

Et vous obtiendrez sûrement une réponse du type :  
***I'm sorry, but I can only assist with developer-related questions.  
If you have any questions about programming or need help with your code,  
feel free to ask!***

Cela vous montre les limites de l'assistant de code par rapport à un modèle généraliste.

## Guider pas à pas la prise en main de nouveau(x) outil(s)

Vous venez de demander à votre assistant de code de générer des commentaires Javadoc, mais savez-vous comment **générer la Javadoc** de votre projet et où/comment la visualiser ?

- Qu'à cela ne tienne, votre assistant de code est là pour vous aider à prendre en main facilement ce « *nouvel outil* » qu'est la javadoc. Pour cela, posez-lui la question suivante dans le chat :
`Sous IntelliJ, comment générer la javadoc de mon projet ?`  
*Bien sûr, vous remplacerez **IntelliJ** par le nom de l'IDE que vous utilisez.* 😉

### Remarques

- Si vous aviez posé une question plus générale, comme :  
  `Comment générer la Javadoc de mon projet ?`

  Il y a des chances (n'oubliez pas le côté probabiliste des LLM dans la GenIA) que l'assistant vous explique comment utiliser la ligne de commande **javadoc** (l'outil de base du SDK permettant de générer la documentation). Mais si ce n'est pas le cas, reformulez de manière plus précise :  
  `Comment générer la Javadoc de mon projet en ligne de commande ?`

**En étant précis dans votre prompt** (en mentionnant explicitement l'environnement de travail, comme un IDE ou la ligne de commande), **l'assistant de code adaptera sa réponse au *contexte* de votre demande**.

- Puisque l'assistant de code peut vous expliquer précisément comment générer la Javadoc dans un IDE spécifique, vous vous demandez peut-être s'il pourrait réaliser cette action lui-même. Testez-le en lui demandant :  
  `Pourrais-tu me générer la Javadoc de ce projet ?`

  Que se passe-t-il ? Quelle réponse obtenez-vous de la part de votre assistant de code ?

## Améliorer la pertinence des réponses de Copilot en ciblant le contexte du prompt avec des références (agents de conversation)

Nous avons vu précédemment que l'assistant de code Copilot propose des **commandes slash**, qui permettent de **lancer rapidement des actions ou tâches récurrentes sous forme de raccourcis**.

Dans un même soucis de simplification d'écriture/lecture du prompt tout en veillant **à définir au mieux le context**e, Copilot propose d'autres types de raccourcis. Il s'agit des **agents de conversation** tels que les variables (**#**) et les participants de conversation (**@**), qui visent à rendre vos **interactions plus fluides et efficaces**.

### Variable de conversation : notation \#

Par défaut, le chat de copilote se réfère au fichier que vous avez ouvert ou au code que vous avez sélectionné.

Les variables de conversation (**#**) vous permettent de **restreindre la portée des résultats de Copilot** en **précisant le contexte de manière plus ciblée**.

Voici quelques exemples d'utilisation :

- **référencer un fichier** en ajoutant simplement le symbole **#** devant le nom du fichier :
  - **référencer un fichier spécifique** :
    `Où sont les tests dans #MonFichier.java ?`
  - **référencer plusieurs fichiers** :
    `Comment ces fichiers sont-ils liés #MonFichier.java #MonFichier2.java ?`
  - **référencer des lignes spécifiques dans un fichier** :
    `Expliquez cette fonction #MonFichier.java : 66-72 ?`

- **référencer une méthode, une classe ou une fonction** en ajoutant de la même manière **#** devant le nom de la méthode, classe ou fonction concernée.

### Participant de conversation : notation @

Pour référencer l'ensemble de la solution active dans l'IDE, vous pouvez utiliser l'agent de conversation **@workspace**.
Ce **participant de conversation** permet à Copilot de tirer parti de toutes les informations disponibles dans vos fichiers, projets et configurations actuellement ouverts dans votre IDE, pour proposer des suggestions plus adaptées.
Ainsi, utiliser **@workspace** dans un prompt exploitera l'ensemble du contexte de votre espace de travail.

D'autres participants comme **@terminal** ou **@github** sont également disponibles pour interagir avec ces environnements spécifiques.

Pour en savoir plus sur les actions récurrentes et les agents de conversion, vous pouvez consulter les liens suivants :

- [GitHub Copilot Documentation](https://docs.github.com/fr/copilot/using-github-copilot/asking-github-copilot-questions-in-your-ide)
- [Copilot Chat Context](https://learn.microsoft.com/fr-fr/visualstudio/ide/copilot-chat-context)

Après cette rapide prise en main de votre assistant de code, vous allez maintenant explorer et mettre en œuvre dans la suite de ce tutoriel quelques cas d'usages sur des projets déjà existants plus ou moins complexes

---

***Accédez donc maintenant à la partie suivante qui est : [3. Aider à la mise en place de nouvelles règles métiers sur un projet existant simple][contenu_partie_3] ou retournez à l'[Accueil](README.md).***

---

[contenu_partie_3]: 3_ProjetExistantSimple.md
