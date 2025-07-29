---
demo:
  title: "Démonstration\_: Générer la documentation du projet à l’aide de GitHub Copilot Chat"
  module: 'Module 2: Generate documentation using GitHub Copilot tools'
---

# Démonstration : Générer la documentation du projet à l’aide de GitHub Copilot Chat

## Instructions

Les activités de la version de démonstration sont conçues pour un environnement qui inclut les ressources suivantes :

- Visual Studio Code.
- L’extension du kit de développement C# pour Visual Studio Code.
- Les extensions GitHub Copilot et GitHub Copilot Chat pour Visual Studio Code. Il est nécessaire de disposer d’un compte GitHub avec un abonnement actif pour GitHub Copilot.
- Des exemples de projets de code créés en C#.

**REMARQUE** : Nous recommandons aux instructeurs d’utiliser leur propre compte GitHub et leur abonnement GitHub Copilot pour les démonstrations. Ainsi vous pouvez contrôler et personnaliser votre environnement de développement. Cette démarche facilite également l’ajustement des démonstrations en fonction des besoins de vos salles de classe.

**IMPORTANT** : Si vous choisissez d’exécuter les démonstrations dans l’environnement de laboratoire hébergé plutôt que sur votre ordinateur personnel instructeur, vous pouvez décompresser les exemples d’applications dans l’environnement hébergé. Vous devez configurer les extensions GitHub Copilot dans l’environnement hébergé avant de pouvoir exécuter les démonstrations. Vous pouvez constater que l’environnement hébergé est plus lent que votre environnement local. Vous devrez probablement ajuster l’allure des démonstrations en conséquence.

### Présentez la version de démonstration

La création de la documentation est une partie importante du développement de logiciels. La documentation en ligne aide les développeurs à comprendre le codebase, sa finalité, et comment l’utiliser. Une documentation de projet fournit aux parties intéressées les informations essentielles à la compréhension de l’étendue et de l’objectif du projet.

Une documentation de projet comprend souvent les sections suivantes :

- **Vue d’ensemble du projet** : Résumé général du projet, de sa finalité et de ses objectifs.
- **Exigences du projet** : Liste des exigences relatives au projet, notamment au niveau des besoins fonctionnels et non fonctionnels.
- **Contraintes du projet** : Toutes les contraintes qui affectent le projet, par exemple les contraintes de temps, de budget ou techniques.
- **Dépendances du projet** : Liste des dépendances du projet, notamment les bibliothèques, les infrastructures et autres composants sur lesquels le projet repose.
- **Résumé du projet** : Bref résumé du projet, de sa finalité et de ses objectifs.

Dans cette version de démonstration, vous utilisez GitHub Copilot Chat pour générer la documentation du projet `APL2007M2Sample1`.

> [!IMPORTANT]
> Les instructeurs doivent souligner l’importance de passer en revue la documentation suggérée par GitHub Copilot. Les développeurs doivent vérifier l’exactitude et l’exhaustivité. La documentation générée par GitHub Copilot est un point de départ. Vous allez peut-être devoir ajouter, supprimer ou modifier le contenu pour répondre aux besoins spécifiques de votre projet.

### Générer une documentation de projet pour le projet APL2007M2Sample1

La documentation du projet peut être générée dans Visual Studio Code à l’aide de la vue Conversation et du participant `@workspace`. Vous pouvez inclure des descriptions en langage naturel pour générer des sections spécifiques de la documentation de projet, par exemple la vue d’ensemble du projet, les exigences, les contraintes, les dépendances et le résumé. Vous pouvez également utiliser GitHub Copilot Chat pour générer des types spécifiques de fichiers de documentation, par exemple un fichier `readme.md`.

1. Vérifiez que le projet `APL2007M2Sample1` est ouvert dans Visual Studio Code.

1. Pour ouvrir l’affichage Conversation, sélectionnez **Ouvrir la conversation**.

1. Dans la vue Conversation, pour générer la documentation de l’espace de travail, entrez le prompt suivant :

    ```output
    @workspace document this project
    ```

1. Prenez une minute pour passer en revue la documentation de projet générée pour le projet `APL2007M2Sample1`.

    Notez que la documentation de projet suggérée est semblable à l’explication de projet générée dans la leçon précédente.

    En ajoutant des prompts, par exemple « documente les contraintes du projet » ou « documente les dépendances du projet », vous pouvez obtenir des informations détaillées sur le projet.

1. Dans la vue Conversation, pour générer de la documentation décrivant les dépendances du projet, entrez le prompt suivant :

    ```output
    @workspace document the project dependencies
    ```

1. Prenez une minute pour passer en revue la documentation sur les dépendances du projet.

    La réponse générée par Copilot Chat doit être semblable aux informations suivantes :

    GitHub Copilot Chat peut vous aider à documenter les proportions de vos projets. Vous pouvez utiliser la vue Conversation afin de générer de la documentation pour des fichiers, des classes ou des fonctions spécifiques au sein du projet. La taille et la complexité du projet permettent de déterminer le niveau de détail nécessaire.

    Si le temps le permet, utilisez la vue Conversation afin de générer une documentation pour les sections suivantes du projet :

    - Configuration requise du projet
    - Contraintes du projet
    - Architecture du projet
    - Conception du projet
    - Test du projet
    - Déploiement du projet
    - Résumé du projet

    Vous pouvez personnaliser la documentation de projet générée par Copilot Chat en fonction des besoins spécifiques de votre projet et de ses parties prenantes.

1. Dans la vue Conversation, si vous souhaitez générer un fichier README pour le projet `APL2007M2Sample1`, entrez le prompt suivant :

    ```output
    @workspace generate a readme document that can be used as a repo description
    ```

1. Prenez une minute pour passer en revue le fichier README généré pour le projet `APL2007M2Sample1`.

    Le contenu de fichier README généré par Copilot Chat fournit une vue d’ensemble générale du projet avec plusieurs sections souvent incluses dans ce type de fichier.

    Vous pouvez ajuster l’invite pour spécifier des sections README spécifiques. Vous pouvez également écrire des prompts individuels pour générer des sections spécifiques d’un document README.

    > [!NOTE]
    > Si vous souhaitez que le document LISEZMOI soit mis en forme comme fichier Markdown, vous pouvez entrer une requête similaire à la suivante : `generate readme project documentation formatted using a raw markdown format`. Si GitHub Copilot est configuré pour fonctionner avec des fichiers Markdown, vous pouvez utiliser la fonctionnalité de conversation inline pour mettre en forme le document README en tant que fichier Markdown.

### Résumé

Dans cette version de démonstration, vous avez utilisé GitHub Copilot Chat pour générer la documentation du projet `APL2007M2Sample1`. En utilisant la vue Conversation et le participant `@workspace`, vous avez pu générer de la documentation pour la vue d’ensemble, les exigences, les contraintes, les dépendances et le résumé du projet. Vous avez également généré un fichier README pour le projet `APL2007M2Sample1`. En utilisant Copilot Chat pour générer une documentation de projet, vous pouvez créer une vue d’ensemble générale qui aide les autres développeurs à comprendre le projet et ses objectifs. N’oubliez pas d’évaluer la documentation générée par Copilot Chat pour garantir la précision et l’exhaustivité.
