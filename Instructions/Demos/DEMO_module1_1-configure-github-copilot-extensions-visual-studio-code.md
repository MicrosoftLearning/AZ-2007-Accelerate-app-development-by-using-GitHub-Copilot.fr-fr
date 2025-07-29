---
demo:
  title: "Démonstration\_: Configurer des extensions GitHub Copilot pour Visual Studio Code"
  module: 'Module 1: Get started with GitHub Copilot'
---

# Démonstration : Configurer des extensions GitHub Copilot pour Visual Studio Code

## Instructions

Les activités de la version de démonstration sont conçues pour un environnement qui inclut les ressources suivantes :

- Visual Studio Code.
- L’extension du kit de développement C# pour Visual Studio Code.
- Les extensions GitHub Copilot et GitHub Copilot Chat pour Visual Studio Code. Il est nécessaire de disposer d’un compte GitHub avec un abonnement actif pour GitHub Copilot.
- Des exemples de projets de code créés en C#.

**REMARQUE** : Nous recommandons aux instructeurs d’utiliser leur propre compte GitHub et leur abonnement GitHub Copilot pour les démonstrations. Ainsi vous pouvez contrôler et personnaliser votre environnement de développement. Cette démarche facilite également l’ajustement des démonstrations en fonction des besoins de vos salles de classe.

**IMPORTANT** : Si vous choisissez d’exécuter les démonstrations dans l’environnement de laboratoire hébergé plutôt que sur votre ordinateur personnel instructeur, vous pouvez décompresser les exemples d’applications dans l’environnement hébergé. Vous devez configurer les extensions GitHub Copilot dans l’environnement hébergé avant de pouvoir exécuter les démonstrations. Vous pouvez constater que l’environnement hébergé est plus lent que votre environnement local. Vous devrez probablement ajuster l’allure des démonstrations en conséquence.

### Présentez la version de démonstration

Les paramètres de GitHub Copilot sont configurés dans votre compte GitHub.com et dans l’environnement Visual Studio Code. Dans Visual Studio Code, vous accédez aux paramètres de GitHub Copilot et GitHub Copilot Chat à l’aide du menu d’état de GitHub Copilot.

Les paramètres de Visual Studio Code vous permettent d’activer ou de désactiver GitHub Copilot pour certains langages, de configurer le comportement de GitHub Copilot Chat et de personnaliser l’expérience GitHub Copilot selon vos préférences. Vous pouvez également configurer les paramètres de GitHub Copilot sur GitHub.com pour gérer votre abonnement GitHub Copilot, configurer la rétention des prompts et des suggestions, et autoriser ou bloquer les suggestions correspondant à du code public.

## Activer ou désactiver GitHub Copilot

GitHub Copilot est activé par défaut lorsque vous installez l’extension dans Visual Studio Code. Vous pouvez désactiver GitHub Copilot pendant un moment au besoin.

Pour afficher les options d’activation et de désactivation de l’extension GitHub Copilot, effectuez ces étapes :

1. Dans Visual Studio Code, ouvrez l’affichage **Extensions**.

1. Dans la liste des extensions installées, faites défiler jusqu’à ce que vous trouviez **GitHub Copilot**.

1. Pour afficher un menu déroulant pour l’extension GitHub Copilot qui répertorie les options Activer et Désactiver, sélectionnez l’icône d’engrenage en regard de GitHub Copilot.

Si vous souhaitez illustrer les options d’activation/désactivation, vous pouvez sélectionner l’option de désactivation. Toutefois, veillez à réactiver GitHub Copilot avant de poursuivre cette version de démonstration.

## Configurer GitHub Copilot et Copilot Chat dans Visual Studio Code

Les extensions GitHub Copilot sont configurées avec les paramètres par défaut lorsque vous les installez dans Visual Studio Code. Vous pouvez personnaliser ces paramètres en fonction de vos préférences.

Visual Studio Code fournit deux manières d’accéder aux paramètres des extensions GitHub Copilot :

- Vous pouvez utiliser l’icône `Manage` pour ouvrir l’onglet Paramètres de Visual Studio Code. Dans l’onglet Paramètres, sélectionnez **Extensions**, puis choisissez **Copilot**.
- Vous pouvez utiliser l’icône d’état de GitHub Copilot pour accéder au menu d’état de GitHub Copilot, puis sélectionner **Modifier les paramètres**.

Illustrez l’utilisation du menu d’état de GitHub Copilot pour accéder aux paramètres. Cette action ouvre l’onglet Paramètres de Visual Studio Code avec un filtre appliqué sur les réglages de GitHub Copilot. L’utilisation du menu d’état est le moyen le plus rapide d’accéder aux paramètres des extensions GitHub Copilot.

### Configurer les paramètres de GitHub Copilot

Pour afficher les paramètres de configuration de GitHub Copilot, procédez comme suit :

1. Dans le volet inférieur de la fenêtre Visual Studio Code, pour ouvrir le menu d’état de GitHub Copilot, sélectionnez l’icône d’état de GitHub Copilot.

    L’icône d’état de GitHub Copilot indique si GitHub Copilot est activé ou désactivé. Lorsqu’il est activé, la couleur d’arrière-plan de l’icône correspond à la couleur de la barre d’état. Lorsqu’il est désactivé, la couleur d’arrière-plan de l’icône contraste avec la couleur de la barre d’état.

1. Dans le menu d’état de GitHub Copilot, sélectionnez **Modifier les paramètres**.

1. Prenez une minute pour passer en revue la liste des paramètres disponibles.

    Notez que les paramètres pour GitHub Copilot et GitHub Copilot Chat sont répertoriés. En outre, sous l’étiquette Extensions à gauche, les deux extensions sont étiquetées « Copilot ». La première extension Copilot correspond à GitHub Copilot, tandis que la seconde correspond à GitHub Copilot Chat.

1. Sous l’étiquette Extensions, sélectionnez la première extension Copilot.

    Notez que la liste des paramètres est désormais filtrée pour GitHub Copilot uniquement.

    Les paramètres de GitHub Copilot incluent les options suivantes :

    - Activer les autocomplétions
    - Activer ou désactiver les complétions Copilot pour des langages spécifiés

1. Prenez une minute pour passer en revue les paramètres de **Enable or disable Copilot completions for specified languages**.

    Notez que les paramètres de cette option sont configurés à l’aide d’une liste de langages et d’une valeur **true** ou **false** pour activer ou désactiver GitHub Copilot pour chaque langage. Par défaut, GitHub Copilot est activé pour tous les langages. Ce paramètre est spécifié avec le caractère générique `*` sur la première ligne et la valeur **true**. Les lignes suivantes spécifient les langages pour lesquels GitHub Copilot est activé ou désactivé. Par exemple, GitHub Copilot est activé pour **C#**, **JavaScript** et **Python**, et désactivé pour **Plaintext** et **Markdown**.

1. Sous **Enable or disable Copilot completions for specified languages**, sélectionnez **markdown**.

    Notez que la valeur de Markdown est définie sur **false**. Cela signifie que GitHub Copilot est désactivé pour les fichiers Markdown.

1. Pour activer Copilot pour les fichiers Markdown, sélectionnez **Edit Item** (icône de crayon), sélectionnez **false**, remplacez la valeur par **true**, puis sélectionnez **OK**.

    Vous pouvez maintenant utiliser des projets de document GitHub Copilot utilisant des fichiers Markdown.

1. Sous l’étiquette Extensions, sélectionnez la deuxième extension Copilot.

    Notez que la liste des paramètres est désormais filtrée pour GitHub Copilot Chat uniquement.

    Les paramètres de GitHub Copilot Chat comprennent les options **Aperçu** et **Expérimental**. Les choix de paramètres comprennent les options suivantes :

    - **Résoudre les problèmes d’échecs de test** : Cette option est activée par défaut afin que GitHub Copilot puisse fournir des suggestions pour résoudre les problèmes d’échecs de test.
    - **Suivis** : Par défaut, ce paramètre est défini sur **firstOnly**, autrement dit GitHub Copilot fournit des suggestions de suivi uniquement après la première suggestion. Les autres options sont **toujours** et **jamais**.
    - **Formule locale** : par défaut, cette option est définie sur **automatique**, ce qui signifie que GitHub Copilot utilise les paramètres régionaux de la langue d’affichage de Visual Studio Code.
    - **Sélection de l’étendue** : cette option est désactivée par défaut. Lorsqu’elle est activée, l’utilisateur est invité à entrer un symbole d’étendue lorsqu’il utilise `/explain` dans Chat sans que rien ne soit sélectionné dans l’éditeur.
    - **Emplacement de la conversation terminale** : Le paramètre par défaut est chatView, qui spécifie l’affichage de conversation. Les autres options sont destinées à la zone Conversation rapide et au terminal.
    - **Utiliser les modèles de projet** : Cette option est activée par défaut afin que GitHub Copilot utilise des modèles de projet GitHub pertinents lorsque l’utilisateur utilise `/new` dans Chat.
    - **Activer les actions de code** : Cette option est activée par défaut afin que GitHub Copilot puisse fournir des actions de code dans l’éditeur.
    - **Déclencher automatiquement** : Cette option est activée par défaut pour que les suggestions GitHub Copilot soient affichées automatiquement à mesure que vous tapez.

    Nous vous recommandons de conserver les paramètres par défaut pendant cette formation. Cela permet d’être sûr de bénéficier de l’expérience attendue lors de l’exécution des modules dans ce parcours d’apprentissage. Une fois la formation terminée, vous pourrez expérimenter ces paramètres pour personnaliser votre expérience avec GitHub Copilot et Copilot Chat.

## Configurer les paramètres de GitHub Copilot sur GitHub.com

Les paramètres de votre compte GitHub sur GitHub.com incluent les options de configuration de GitHub Copilot. Ces paramètres sont utilisés pour gérer votre abonnement GitHub Copilot, configurer la rétention des prompts et des suggestions, et autoriser ou bloquer les suggestions correspondant à du code public.

GitHub Copilot peut être géré via des comptes personnels avec GitHub Copilot Individual, ou via des comptes organisationnels avec GitHub Copilot Business/Enterprise.

## Raccourcis clavier pour GitHub Copilot

Vous pouvez utiliser les raccourcis clavier par défaut dans Visual Studio Code lors de l’utilisation de GitHub Copilot. Vous pouvez également lier à nouveau les raccourcis dans l’éditeur Raccourcis clavier à l’aide de vos raccourcis clavier préférés pour chaque commande spécifique.
