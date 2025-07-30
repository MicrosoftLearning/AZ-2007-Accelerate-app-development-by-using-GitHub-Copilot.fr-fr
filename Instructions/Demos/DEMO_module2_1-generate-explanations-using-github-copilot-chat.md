---
demo:
  title: "Démonstration\_: Générer des explications de code à l’aide de GitHub Copilot Chat"
  module: 'Module 2: Generate documentation using GitHub Copilot tools'
---

# Démonstration : Générer des explications de code à l’aide de GitHub Copilot Chat

## Instructions

Les activités de la version de démonstration sont conçues pour un environnement qui inclut les ressources suivantes :

- Visual Studio Code.
- L’extension du kit de développement C# pour Visual Studio Code.
- Les extensions GitHub Copilot et GitHub Copilot Chat pour Visual Studio Code. Il est nécessaire de disposer d’un compte GitHub avec un abonnement actif pour GitHub Copilot.
- Des exemples de projets de code créés en C#.

**REMARQUE** : Nous recommandons aux instructeurs d’utiliser leur propre compte GitHub et leur abonnement GitHub Copilot pour les démonstrations. Ainsi vous pouvez contrôler et personnaliser votre environnement de développement. Cette démarche facilite également l’ajustement des démonstrations en fonction des besoins de vos salles de classe.

**IMPORTANT** : Si vous choisissez d’exécuter les démonstrations dans l’environnement de laboratoire hébergé plutôt que sur votre ordinateur personnel instructeur, vous pouvez décompresser les exemples d’applications dans l’environnement hébergé. Vous devez configurer les extensions GitHub Copilot dans l’environnement hébergé avant de pouvoir exécuter les démonstrations. Vous pouvez constater que l’environnement hébergé est plus lent que votre environnement local. Vous devrez probablement ajuster l’allure des démonstrations en conséquence.

### Présentez la version de démonstration

GitHub Copilot Chat utilise l’assistance de l’IA conversationnelle et les commandes intelligentes pour vous aider dans des tâches relatives au code. L’un des exemples est la possibilité d’expliquer un code inconnu et complexe.

Vous pouvez utiliser GitHub Copilot Chat pour générer des explications pour plusieurs raisons. Par exemple :

- GitHub Copilot Chat peut vous expliquer un espace de travail entier ou des fichiers projet spécifiques lorsque vous rejoignez un projet existant.
- GitHub Copilot Chat peut vous expliquer des lignes de code ou des sections spécifiques lorsque le code est complexe ou difficile à comprendre.
- GitHub Copilot Chat peut expliquer les erreurs présentes dans votre code et suggérer des façons de les corriger.
- GitHub Copilot Chat peut vous expliquer comment ajouter des fonctionnalités à votre projet et fournir des extraits de code qui montrent comment implémenter le nouveau code.

### Explications sur l’espace de travail et les fichiers projet

GitHub Copilot Chat peut vous aider à comprendre les nouveaux projets ou des fichiers projet spécifiques. Vous pouvez utiliser une combinaison `@workspace`, `/explain` et `#file` dans la vue de conversation ou une fenêtre de conversation rapide pour générer une explication sur votre projet ou des fichiers projet spécifiques.

Utilisez les étapes suivantes pour terminer cette section de la version de démonstration :

1. Ouvrez le dossier **APL2007M2Sample1** dans Visual Studio Code.

    1. Ouvrez Visual Studio Code sur votre PC.
    1. Dans Visual Studio Code, dans le menu **Fichier**, sélectionnez **Ouvrir un dossier**.
    1. Accédez au dossier Bureau de Windows, ouvrez le dossier **SampleApps**, puis repérez le dossier **APL2007M2Sample1**.
    1. Sélectionnez **APL2007M2Sample1**, puis **Sélectionner le dossier**.

    La vue Explorateur de Visual Studio Code doit afficher un projet de code APL2007M2Sample1 contenant les fichiers suivants :

    - APL2007M2Sample1.csproj
    - APL2007M2Sample1.sln
    - App.xaml
    - App.xaml.cs
    - MainWindow.xaml
    - MainWindow.xaml.cs

1. Dans la barre de menu supérieure de Visual Studio Code, sélectionnez **Ouvrir une conversation**.

    Le bouton Ouvrir une conversation se trouve dans la barre de menus située en haut de la fenêtre Visual Studio Code, juste à droite de la zone de recherche. Il est représenté par un petit logo GitHub Copilot.

1. Utilisez la commande suivante pour demander à Copilot Chat d’expliquer le projet `APL2007M2Sample1` :

    ```plaintext
    @workspace Explain this project
    ```

1. Prenez une minute pour examiner la réponse dans la vue de conversation.

    GitHub Copilot Chat génère une explication du projet APL2007M2Sample1 semblable à la réponse suivante :

    > [!IMPORTANT]
    > GitHub Copilot Chat utilise un modèle IA pour générer des réponses. Les réponses que vous recevez sont semblables aux réponses présentées dans cette formation, sans être identiques.

1. Au bas de la vue de conversation, notez que GitHub Copilot Chat a suggéré une question de suivi.

    La réponse que vous recevez peut inclure une question de suivi différente.

    GitHub Copilot Chat génère l’historique de votre conversation. L’historique permet à GitHub Copilot Chat de comprendre vos centres d’intérêt. Lorsque vous créez un historique de conversation, le modèle IA apprend à partir de vos interactions et fournit des questions de suivi plus pertinentes. Nous ne recommandons pas l’exploration de questions de suivi « aléatoires ».

1. Ouvrez le fichier `MainWindow.xaml.cs` dans l’éditeur.

1. Utilisez la commande suivante pour demander à Copilot d’expliquer le fichier `MainWindow.xaml.cs` :

    ```plaintext
    @workspace /explain #file:MainWindow.xaml.cs
    ```

1. Prenez une minute pour examiner la réponse dans la vue de conversation.

    Notez que GitHub Copilot Chat génère une explication détaillée du fichier `MainWindow.xaml.cs`. L’explication comprend des informations sur l’objectif, la structure et les principaux composants du fichier. Vous pouvez également voir une section décrivant les problèmes et les améliorations possibles.

    Encore une fois, GitHub Copilot Chat suggère une question de suivi.

    > [!IMPORTANT]
    > GitHub Copilot Chat tient à jour un historique de votre conversation. Il affine ses réponses en fonction des questions que vous lui posez au fil du temps. Le contexte de vos questions, en particulier celles qui concernent votre projet de code, influence les réponses ultérieures de GitHub Copilot Chat. Cela lui permet de fournir des réponses plus précises et pertinentes. Cela signifie également que la réponse obtenue pour une question déterminée peut varier en fonction de votre historique de conversation.

### Explications concernant le code sélectionné

Même les développeurs expérimentés peuvent avoir des difficultés à comprendre du code. Plutôt que de passer du temps à essayer de déchiffrer du code complexe, vous pouvez demander à GitHub Copilot Chat de fournir une explication. La vue de conversation, la conversation en ligne et les actions intelligentes peuvent chacune être utilisées pour générer des explications pour les lignes de code ou les sections sélectionnées.

Dans cette section de la version de démonstration, vous utilisez l’action intelligente **Expliquer** pour générer une explication des lignes de code sélectionnées.

1. Assurez-vous que le fichier `MainWindow.xaml.cs` est ouvert dans l’éditeur.

1. Faites défiler l’écran vers le bas jusqu’à trouver la méthode `SumPageSizesAsync()`.

    ```csharp

    private async Task SumPageSizesAsync()
    {
        var stopwatch = Stopwatch.StartNew();
        IEnumerable<Task<int>> downloadTasksQuery =
            from url in _urlList
            select ProcessUrlAsync(url, _client);
        Task<int>[] downloadTasks = downloadTasksQuery.ToArray();
        int[] lengths = Task.WhenAll(downloadTasks);
        int total = lengths.Sum();
        await Dispatcher.BeginInvoke(() =>
        {
            stopwatch.Stop();
    
            _resultsTextBox.Text += $"\nTotal bytes returned:  {total:#,#}";
            _resultsTextBox.Text += $"\nElapsed time:          {stopwatch.Elapsed}\n";
        });
    }

    ```

1. Sélectionnez les lignes de code suivantes, puis utilisez l’action intelligente **Expliquer** pour générer une explication.

    Pour sélectionner l’action intelligente **Expliquer**, cliquez avec le bouton droit sur les lignes de code sélectionnées, sélectionnez **Copilot**, puis **Expliquer** dans le menu contextuel.

    ```csharp

    IEnumerable<Task<int>> downloadTasksQuery =
        from url in _urlList
        select ProcessUrlAsync(url, _client);
    Task<int>[] downloadTasks = downloadTasksQuery.ToArray();

    ```

1. Prenez une minute pour examiner la réponse dans la vue de conversation.

1. Remarquez que le niveau de détail dans l’explication.

    GitHub Copilot Chat génère des explications détaillées qui comprennent des informations sur les lignes de code sélectionnées, leur objectif et leur fonctionnement. Les réponses contiennent des extraits de code et des descriptions en langage naturel qui vous aident à comprendre le code.

### Explications concernant les erreurs

La gestion des erreurs est un aspect essentiel du développement de logiciels. Si certaines erreurs sont faciles à repérer et à corriger, d’autres peuvent être plus ardues. Lorsque vous avez des difficultés à comprendre une erreur présente dans votre code, vous pouvez demander à GitHub Copilot Chat de fournir une explication. Par exemple, vous pouvez demander à GitHub Copilot Chat d’expliquer pourquoi une ligne de code déterminée provoque une erreur.

Utilisez les étapes suivantes pour terminer cette section de la version de démonstration :

1. Vérifiez que `MainWindow.xaml.cs` est ouvert dans l’éditeur.

1. Dans la méthode `SumPageSizesAsync()`, recherchez la ligne de code suivante :

    ```csharp
    int[] lengths = Task.WhenAll(downloadTasks);
    ```

1. Placez le curseur de la souris sur `downloadTasks` pour afficher le message d’erreur.

    Les messages d’erreur n’expliquent pas toujours comment corriger des problèmes de codage. Lorsque la solution n’est pas évidente, vous pouvez demander à GitHub Copilot Chat d’expliquer une erreur et de suggérer les moyens de la corriger.

1. Sélectionnez la ligne de code contenant l’erreur, puis appuyez sur **Ctrl + I** pour ouvrir une conversation inline.

1. Si vous souhaitez générer une explication de l’erreur, entrez l’invite suivante :

    ```plaintext
    /explain why is the selection causing an error
    ```

1. Prenez une minute pour examiner la réponse dans la vue de conversation.

    Notez que la réponse comporte des informations sur l’erreur et des suggestions pour la corriger. Dans ce cas, GitHub Copilot Chat explique que la ligne `Task.WhenAll(downloadTasks)` provoque une erreur en raison de l’absence du mot clé `await`. La réponse fournit également un extrait de code qui montre comment corriger l’erreur en ajoutant le mot clé `await` avant la ligne `Task.WhenAll(downloadTasks)`.

1. Utilisez les explications fournies par GitHub Copilot Chat pour corriger les erreurs présentes dans votre code.

    Ajoutez le mot clé `await` avant la ligne de `Task.WhenAll(downloadTasks)`, comme indiqué dans l’extrait de code suivant :

    ```csharp
    int[] lengths = await Task.WhenAll(downloadTasks);
    ```

    Une fois cette modification effectuée, l’erreur devrait être résolue.

### Explications concernant les nouvelles fonctions ou fonctionnalités

GitHub Copilot Chat peut expliquer comment ajouter de nouvelles caractéristiques ou fonctionnalités à votre projet.

Considérez le projet APL2007M2Sample1. Votre code télécharge les pages web et calcule la taille totale des pages téléchargées. Supposons que vous devez ajouter une exception gérant l’application. Dans cette section de la version de démonstration, vous utilisez GitHub Copilot Chat pour expliquer comment gérer les exceptions pendant le processus de téléchargement.

Utilisez les étapes suivantes pour terminer cette section de la version de démonstration :

1. Sélectionnez les lignes de code qui incluent les méthodes `SumPageSizesAsync` et `ProcessUrlAsync`.

1. Dans la vue de conversation, pour demander à GitHub Copilot Chat de vous expliquer comment gérer les exceptions levées pendant le processus de téléchargement, entrez la question suivante :

    ```plaintext
    @workspace /explain #MainWindow.xaml.cs How can I handle exceptions thrown during the download process?
    ```

1. Prenez une minute pour examiner la réponse dans la vue de conversation.

    Copilot Chat génère une réponse similaire à l’explication suivante :

    La réponse fournit une explication sur la façon de gérer les exceptions levées pendant le processus de téléchargement. Vous obtenez également un extrait de code qui implémente le code suggéré de gestion des exceptions. Vous pouvez copier l’extrait de code ou l’insérer dans votre projet de code à l’emplacement du curseur.

    Au lieu de copier ou d’insérer l’extrait de code à partir de la vue Conversation, l’étape suivante examine l’utilisation de la conversation inlined pour implémenter le code de gestion des exceptions suggéré.

1. Pour demander à la conversation inline comment mettre en œuvre la gestion des exceptions, sélectionnez la méthode `ProcessUrlAsync`, appuyez sur **Ctrl + I**, puis saisissez l’invite suivante :

    ```plaintext
    How can I handle exceptions thrown during the download process?
    ```

1. Prenez une minute pour examiner la réponse en ligne.

1. Pour accepter le code de gestion des erreurs proposé, sélectionnez **Accept** (Accepter).

    Notez que le bloc `try-catch` proposé est implémenté.

### Résumé

Dans cette version de démonstration, vous avez utilisé GitHub Copilot Chat pour générer des explications sur les lignes de code, les erreurs et les nouvelles fonctionnalités. GitHub Copilot Chat propose un ensemble puissant de fonctionnalités qui peuvent vous aider à monter rapidement en puissance sur un nouveau projet. En utilisant la conversation en ligne et la vue de conversation, vous pouvez obtenir l’aide de GitHub Copilot Chat sans quitter l’environnement Visual Studio Code. Le modèle d’IA de GitHub Copilot Chat génère des réponses précises et utiles qui peuvent vous aider à faire de vous un développeur plus efficient et efficace.
