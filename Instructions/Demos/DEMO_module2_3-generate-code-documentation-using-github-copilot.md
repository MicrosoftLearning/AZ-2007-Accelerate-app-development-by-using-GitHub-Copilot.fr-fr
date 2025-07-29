---
demo:
  title: "Démonstration\_: Générer la documentation du code inline à l’aide de GitHub Copilot Chat"
  module: 'Module 2: Generate documentation using GitHub Copilot tools'
---

# Démonstration : Générer la documentation du code inline à l’aide de GitHub Copilot Chat

## Instructions

Les activités de la version de démonstration sont conçues pour un environnement qui inclut les ressources suivantes :

- Visual Studio Code.
- L’extension du kit de développement C# pour Visual Studio Code.
- Les extensions GitHub Copilot et GitHub Copilot Chat pour Visual Studio Code. Il est nécessaire de disposer d’un compte GitHub avec un abonnement actif pour GitHub Copilot.
- Des exemples de projets de code créés en C#.

**REMARQUE** : Nous recommandons aux instructeurs d’utiliser leur propre compte GitHub et leur abonnement GitHub Copilot pour les démonstrations. Ainsi vous pouvez contrôler et personnaliser votre environnement de développement. Cette démarche facilite également l’ajustement des démonstrations en fonction des besoins de vos salles de classe.

**IMPORTANT** : Si vous choisissez d’exécuter les démonstrations dans l’environnement de laboratoire hébergé plutôt que sur votre ordinateur personnel instructeur, vous pouvez décompresser les exemples d’applications dans l’environnement hébergé. Vous devez configurer les extensions GitHub Copilot dans l’environnement hébergé avant de pouvoir exécuter les démonstrations. Vous pouvez constater que l’environnement hébergé est plus lent que votre environnement local. Vous devrez probablement ajuster l’allure des démonstrations en conséquence.

### Présentez la version de démonstration

La documentation de votre code est un aspect important du processus de développement logiciel. La documentation incorporée (commentaires de code) aide les développeurs à comprendre le codebase, sa finalité et son utilisation.

GitHub Copilot Chat peut vous aider à documenter votre code de manière rapide et précise. Pour générer une documentation incorporée à l’aide de GitHub Copilot Chat, vous avez plusieurs options :

- Créer votre propre prompt en langage naturel pour générer une documentation spécifique.
- Utiliser la commande `/doc` pendant une session de conversation incorporée pour générer des commentaires sur le code sélectionné.
- Utiliser l’action intelligente **Générer de la documentation** pour générer des commentaires sur le code sélectionné.

La documentation pertinente de votre code crée un codebase plus lisible et plus facile à maintenir que les autres développeurs peuvent facilement comprendre et utiliser.

### Générer la documentation de code en ligne à l’aide de la vue Conversation

Dans cette version de démonstration, vous utilisez GitHub Copilot Chat pour générer la documentation de code inline pour le projet `APL2007M2Sample1`.

Utilisez les étapes suivantes pour terminer cette section de la version de démonstration :

1. Vérifiez que le projet `APL2007M2Sample1` est ouvert dans Visual Studio Code.

1. Ouvrez le fichier `MainWindow.xaml.cs` .

1. Sélectionnez tout le code commençant par la déclaration d’espace de noms jusqu’à la fin du fichier.

1. Ouvrez la vue Conversation.

1. Pour voir comment GitHub Copilot Chat documenterait le code sélectionné, entrez l’invite suivante :

    ```output
    @workspace #selection generate inline code documentation for the selected code
    ```

1. Prenez une minute pour passer en revue la documentation de code suggérée.

    La réponse générée doit ressembler à l’exemple de code suivant :

    ```csharp

    namespace ParallelAsyncExample
    {
        public partial class MainWindow : Window
        {
            // HttpClient instance with a maximum response content buffer size of 1,000,000 bytes
            private readonly HttpClient _client = new HttpClient { MaxResponseContentBufferSize = 1_000_000 };
            // List of URLs to download content from
            private readonly IEnumerable<string> _urlList = new string[]
            {
                "https://docs.microsoft.com",
                "https://docs.microsoft.com/azure",
                "https://docs.microsoft.com/powershell",
                "https://docs.microsoft.com/dotnet",
                "https://docs.microsoft.com/aspnet/core",
                "https://docs.microsoft.com/windows",
                "https://docs.microsoft.com/office",
                "https://docs.microsoft.com/enterprise-mobility-security",
                "https://docs.microsoft.com/visualstudio",
                "https://docs.microsoft.com/microsoft-365",
                "https://docs.microsoft.com/sql",
                "https://docs.microsoft.com/dynamics365",
                "https://docs.microsoft.com/surface",
                "https://docs.microsoft.com/xamarin",
                "https://docs.microsoft.com/azure/devops",
                "https://docs.microsoft.com/system-center",
                "https://docs.microsoft.com/graph",
                "https://docs.microsoft.com/education",
                "https://docs.microsoft.com/gaming"
            };
            // Event handler for the start button click event
            private void OnStartButtonClick(object sender, RoutedEventArgs e)
            {
                // Disable the start button and clear the results text box
                _startButton.IsEnabled = false;
                _resultsTextBox.Clear();
                // Start the asynchronous operation to sum page sizes
                Task.Run(() => StartSumPageSizesAsync());
            }
            // Starts the asynchronous operation to sum page sizes
            private async Task StartSumPageSizesAsync()
            {
                // Perform the main download operation
                await SumPageSizesAsync();
                // Update the UI to re-enable the start button and indicate that control has returned
                await Dispatcher.BeginInvoke(() =>
                {
                    _resultsTextBox.Text += $"\nControl returned to {nameof(OnStartButtonClick)}.";
                    _startButton.IsEnabled = true;
                });
            }
            // Asynchronously sums the sizes of the pages from the URLs
            private async Task SumPageSizesAsync()
            {
                // Start a stopwatch to measure elapsed time
                var stopwatch = Stopwatch.StartNew();
                // Create tasks to download content from each URL
                IEnumerable<Task<int>> downloadTasksQuery =
                    from url in _urlList
                    select ProcessUrlAsync(url, _client);
                // Convert the sequence of tasks into an array
                Task<int>[] downloadTasks = downloadTasksQuery.ToArray();
                // Wait for all tasks to complete and sum the lengths of the downloaded content
                int[] lengths = await Task.WhenAll(downloadTasks);
                int total = lengths.Sum();
                // Update the UI with the total bytes and elapsed time
                await Dispatcher.BeginInvoke(() =>
                {
                    stopwatch.Stop();
                    _resultsTextBox.Text += $"\nTotal bytes returned:  {total:#,#}";
                    _resultsTextBox.Text += $"\nElapsed time:          {stopwatch.Elapsed}\n";
                });
            }
            // Asynchronously processes a URL by downloading its content and returning the length of the content
            private async Task<int> ProcessUrlAsync(string url, HttpClient client)
            {
                try
                {
                    // Download the content of the URL
                    byte[] byteArray = await client.GetByteArrayAsync(url);
                    // Update the UI with the URL and content length
                    await DisplayResultsAsync(url, byteArray);
                    // Return the length of the downloaded content
                    return byteArray.Length;
                }
                catch (HttpRequestException e)
                {
                    // Handle HTTP request exceptions by updating the UI with an error message
                    await Dispatcher.BeginInvoke(() =>
                    {
                        _resultsTextBox.Text += $"{url,-60} {"Error",-10}\n";
                        _resultsTextBox.Text += $"Exception: {e.Message}\n";
                    });
                    // Return 0 to indicate failure
                    return 0;
                }
            }
            // Updates the UI with the URL and the length of the downloaded content
            private Task DisplayResultsAsync(string url, byte[] content) =>
                Dispatcher.BeginInvoke(() =>
                    _resultsTextBox.Text += $"{url,-60} {content.Length,10:#,#}\n")
                          .Task;
            // Disposes of the HttpClient instance when the window is closed to free up resources
            protected override void OnClosed(EventArgs e) => _client.Dispose();
        }
    }

    ```

    La réponse inclut des commentaires de code suggérés et *une partie* du code associé. Vous pouvez omettre une partie de votre code par souci de concision. Vous pouvez déplacer manuellement des commentaires de code dans le fichier de code réel.

    La conversation incorporée offre un moyen plus direct d’ajouter des commentaires à votre code.

### Générer la documentation de code en ligne à l’aide de la conversation en ligne

1. Faites défiler l’écran jusqu’en haut du fichier `MainWindow.xaml.cs`.

1. Sélectionnez la méthode `OnStartButtonClick`.

1. Pour ouvrir une conversation inline, appuyez sur **Ctrl+I**.

1. Pour générer la documentation en ligne pour la méthode `OnStartButtonClick`, entrez l’invite suivante :

    ```output
    /doc
    ```

1. Prenez une minute pour passer en revue la documentation de code générée.

    Notez que la documentation suggérée pour la méthode `OnStartButtonClick` inclut un résumé et des descriptions des deux paramètres. Lorsqu’une méthode inclut une valeur de retour, une description de la valeur de retour est également incluse.

    > [!IMPORTANT]
    > Passez toujours en revue les mises à jour suggérées par GitHub Copilot avant d’accepter. Si vous détectez un problème dans une mise à jour de code suggérée, vous pouvez ignorer la mise à jour ou tenter de corriger le problème avant d’accepter la mise à jour de code suggérée.

1. Pour ignorer la mise à jour suggérée, sélectionnez **Ignorer**.

    Dans la section suivante, vous générez de la documentation pour toutes les méthodes en même temps.

### Générer la documentation de code en ligne à l’aide de l’action intelligente **Générer la documentation**

L’action intelligente **Générer des documents** est une autre façon de générer la documentation du code inlined. Vous pouvez utiliser cette action intelligente pour générer des commentaires décrivant le code sélectionné.

Utilisez les étapes suivantes pour terminer cette section de la version de démonstration :

1. Dans l’éditeur Visual Studio Code, sélectionnez toutes les méthodes *à l’intérieur* de la classe `MainWindow`.

1. Cliquez avec le bouton droit sur le code sélectionné, sélectionnez **Copilot**, puis **Générer la documentation**.

    Attendez que la documentation soit générée.

1. Passez en revue les modifications suggérées.

    > [!IMPORTANT]
    > Si vous trouvez des problèmes dans la documentation générée, modifiez les modifications suggérées avant de continuer.

1. Sélectionnez **Accepter**.

    Chacune des méthodes de la classe `MainWindow` contient désormais des commentaires générés.

### Résumé

Dans cette version de démonstration, vous avez utilisé GitHub Copilot Chat pour générer la documentation de code en ligne pour l’application `APL2007M2Sample1`. Vous avez appris à générer la documentation de code en ligne à l’aide de la vue Conversation, de la conversation en ligne et de l’action intelligente **Générer la documentation**. La génération de commentaires de code vous permet de créer un codebase plus lisible et plus facile à maintenir que les autres développeurs peuvent facilement comprendre et utiliser. La documentation de code en ligne est une partie essentielle du développement logiciel qui permet aux développeurs de comprendre le codebase, son objectif et comment l’utiliser.
