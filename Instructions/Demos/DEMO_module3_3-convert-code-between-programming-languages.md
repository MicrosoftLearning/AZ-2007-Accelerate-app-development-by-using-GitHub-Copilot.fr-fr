---
demo:
  title: "Démonstration\_: Convertir du code d’un langage de programmation en un autre"
  module: 'Module 3: Develop code features using GitHub Copilot tools'
---

# Démonstration : Convertir du code d’un langage de programmation en un autre

## Instructions

Les activités de version de démonstration sont conçues pour un environnement qui inclut les ressources suivantes :

- Visual Studio Code.
- L’extension du kit de développement C# pour Visual Studio Code.
- Les extensions GitHub Copilot et GitHub Copilot Chat pour Visual Studio Code. Il est nécessaire de disposer d’un compte GitHub avec un abonnement actif pour GitHub Copilot.
- Des exemples de projets de code créés en C#.

**REMARQUE** : Nous recommandons aux instructeurs d’utiliser leur propre compte GitHub et leur abonnement GitHub Copilot pour les démonstrations. Ainsi vous pouvez contrôler et personnaliser votre environnement de développement. Cette démarche facilite également l’ajustement des démonstrations en fonction des besoins de vos salles de classe.

**IMPORTANT** : Si vous choisissez d’exécuter les démonstrations dans l’environnement de laboratoire hébergé plutôt que sur votre ordinateur personnel instructeur, vous pouvez décompresser les exemples d’applications dans l’environnement hébergé. Vous devez configurer les extensions GitHub Copilot dans l’environnement hébergé avant de pouvoir exécuter les démonstrations. Vous pouvez constater que l’environnement hébergé est plus lent que votre environnement local. Vous devrez peut-être donc ajuster l’allure des démonstrations en conséquence.

### Présentation de la version de démonstration

GitHub Copilot peut vous aider à convertir du code d’un langage de programmation en un autre. Par exemple, vous pouvez demander à GitHub Copilot de convertir une fonction ou un extrait de code en un autre langage de programmation.

Vous pouvez effectuer les types de conversions de code suivants à l’aide de GitHub Copilot :

- Convertir un fichier de code entier en un autre langage de programmation.
- Convertir une fonction en un autre langage de programmation.
- Convertir un extrait de code en un autre langage de programmation.

Chacune des interfaces de conversation (vue Conversation, fenêtre Conversation rapide et conversation en ligne) peut être utilisée pour convertir du code entre différents langages de programmation. Votre choix d’interface de conversation dépend de vos préférences et de la complexité du code que vous souhaitez convertir.

Supposons que vous commencez simplement sur le projet `QuarterlyIncomeReport`. Vous discutez des objectifs du projet avec un collègue. Ils mentionnent qu’ils ont un fichier Python qui peut fournir certaines des fonctionnalités que vous recherchez. Ils vous montrent le référentiel pour le code Python. Vous décidez d’ouvrir le projet de code Python dans Visual Studio Code et d’utiliser la vue Conversation pour convertir le code Python en C#.

## Convertir du code entre différents langages de programmation à l’aide de la vue Conversation

1. Ouvrez le dossier du projet **APL2007M3Python** dans Visual Studio Code.

    Ce projet contient une version Python du projet `QuarterlyIncomeReport` sur lequel vous avez travaillé au cours de ce module. GitHub Copilot peut vous expliquer le code à l’aide de la vue Conversation ou de l’action intelligente Expliquer ceci.

1. Exécuter l’application Python.

    Notez que la sortie de l’application Python est essentiellement la même que la sortie de l’application C# que vous avez créée précédemment.

1. Ouvrez le fichier Python `main.py`.

    Le fichier Python contient une fonction qui génère des données de vente. Vous souhaitez convertir ce code Python en C#.

1. Sélectionnez l’intégralité du contenu du fichier.

1. Ouvrez la vue Conversation, puis entrez l’invite suivante :

    ```plaintext
    Convert #selection to C#
    ```

1. Prenez un moment pour passer en revue la réponse de GitHub Copilot.

    La réponse doit contenir la version C# du code Python que vous avez sélectionnée.

1. Ouvrez une deuxième instance de Visual Studio Code.

1. Ouvrez la vue Conversation, puis entrez l’invite suivante :

    ```plaintext
    @workspace /new console application in C# NET8 named APL2007M3B. Only .cs and .csproj files. Enable ImplicitUsings and Nullable
    ```

    Si Copilot répond avec un message d’erreur concernant l’argument de chemin, réessayez la même invite.

1. Sélectionnez **Créer un espace de travail**

1. Dans la boîte de dialogue Ouvrir un dossier, sélectionnez le dossier **Desktop**, puis **Sélectionner en tant que dossier parent**.

    attendez que l’espace de travail soit créé.

1. Lorsque l’espace de travail est créé, sélectionnez **Program.cs**, puis supprimez le contenu du fichier.

1. Basculez vers l’instance de Visual Studio Code qui contient le code Python.

1. Faites défiler vers le haut de la vue Conversation, puis cliquez sur le bouton **Copier** pour copier le code C# généré dans le Presse-papiers.

1. Basculez vers l’instance de Visual Studio Code qui contient le code C#.

1. Collez le code C# dans le fichier Program.cs.

1. Enregistrez le fichier Program.cs.

1. Exécutez l’application C#.

    Notez que la sortie de l’application C# est essentiellement la même que la sortie de l’application Python.

    Si vous avez du temps, prenez quelques minutes pour passer en revue les différences entre le code C# converti et le code C# de l’unité précédente.

## Convertir du code entre différents langages de programmation à l’aide de la conversation en ligne

1. Revenez à l’instance Visual Studio Code contenant le projet Python que vous avez ouvert précédemment.

1. Sélectionnez le code dans le fichier main.py.

1. Ouvrez la conversation en ligne, puis entrez l’invite suivante :

    ```plaintext
    Convert #selection to C#
    ```

1. Examinez la réponse de GitHub Copilot, puis sélectionnez **Accepter**.

    Le fichier Python doit maintenant contenir du code C#.

1. Copiez le code C# généré dans le Presse-papiers.

1. Fermez le fichier main.py sans enregistrer les modifications.

1. Basculez vers l’instance de Visual Studio Code qui contient le projet C# et ouvrez le fichier Program.cs.

1. Pour remplacer le code C# existant, collez le code C# du Presse-papiers (converti à partir de Python à l’aide de la conversation en ligne) sur le contenu du fichier Program.cs.

1. Enregistrez le fichier Program.cs.

1. Exécutez l’application C#.

    Notez que la sortie de l’application C# est essentiellement la même que la sortie de l’application Python.

Lorsque vous utilisez GitHub Copilot pour convertir du code entre différents langages de programmation, essayez d’utiliser à la fois la vue Conversation et dans la conversation en ligne. Bien que les deux outils partagent le même modèle IA, leurs résultats peuvent différer. Essayer les deux outils peut vous aider à déterminer l’outil le mieux adapté à votre cas d’usage spécifique.

> [!NOTE]
> Les langages de programmation ont souvent un « style de programmation » associé, et certains langages peuvent avoir des fonctionnalités ou des bibliothèques de code uniques. Lorsque vous convertissez de grandes sections de code d’un langage de programmation à un autre, il est important de bien comprendre le langage de programmation cible et l’intention du code. Vous devez toujours passer en revue les suggestions de GitHub Copilot avant de les accepter.

### Résumé

Dans cette version de démonstration, vous avez utilisé GitHub Copilot pour convertir du code Python en C#. Vous avez utilisé la vue Conversation et la conversation inline pour convertir le code Python en C#. Vous avez ensuite exécuté l’application C# pour vérifier que la sortie était identique à celle de l’application Python. Lorsque vous utilisez GitHub Copilot pour convertir du code entre des langages de programmation, vous pouvez rapidement adapter le code d’un langage à l’autre. N’oubliez pas d’examiner le code converti pour vous assurer qu’il répond à vos exigences et qu’il respecte le style de programmation du langue cible.
