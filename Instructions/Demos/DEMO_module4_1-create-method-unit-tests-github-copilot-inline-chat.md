---
demo:
  title: "Démonstration\_: Créer des tests unitaires à l’aide de GitHub Copilot Chat"
  module: 'Module 4: Develop unit tests using GitHub Copilot tools'
---

# Démonstration : Créer des tests unitaires à l’aide de GitHub Copilot Chat

## Instructions

Les activités de la version de démonstration sont conçues pour un environnement qui inclut les ressources suivantes :

- Visual Studio Code.
- L’extension du kit de développement C# pour Visual Studio Code.
- Les extensions GitHub Copilot et GitHub Copilot Chat pour Visual Studio Code. Il est nécessaire de disposer d’un compte GitHub avec un abonnement actif pour GitHub Copilot.
- Des exemples de projets de code créés en C#.

**REMARQUE** : Nous recommandons aux instructeurs d’utiliser leur propre compte GitHub et leur abonnement GitHub Copilot pour les démonstrations. Ainsi vous pouvez contrôler et personnaliser votre environnement de développement. Cette démarche facilite également l’ajustement des démonstrations en fonction des besoins de vos salles de classe.

**IMPORTANT** : Si vous choisissez d’exécuter les démonstrations dans l’environnement de laboratoire hébergé plutôt que sur votre ordinateur personnel instructeur, vous pouvez décompresser les exemples d’applications dans l’environnement hébergé. Vous devez configurer les extensions GitHub Copilot dans l’environnement hébergé avant de pouvoir exécuter les démonstrations. Vous pouvez constater que l’environnement hébergé est plus lent que votre environnement local. Vous devrez probablement ajuster l’allure des démonstrations en conséquence.

### Présentez la version de démonstration

Visual Studio Code et C# Dev Kit fournissent un vaste ensemble de fonctionnalités qui vous aident à créer et gérer des tests unitaires pour vos projets C#. Vous pouvez activer les tests pour votre projet, ajouter des packages d’infrastructure de test, exécuter et gérer des tests unitaires et générer des cas de test unitaire à l’aide du kit de développement C#.

GitHub Copilot peut vous aider à générer des tests unitaires pour votre code en fournissant des suggestions de conversation inline.

Dans cette version de démonstration, vous allez créer des tests unitaires pour un projet de code à l’aide de GitHub Copilot Chat dans Visual Studio Code.

### Créer un projet de test xUnit pour vos tests unitaires

Les projets de test unitaire sont généralement créés dans un dossier distinct du projet que vous testez. Cette séparation permet de séparer le code de test du code de production. Dans cette version de démonstration, vous créez un projet de test xUnit pour le projet APL2007M4PrimeService.

Pour créer un projet de test xUnit, procédez comme suit :

1. Ouvrez le dossier **APL2007M4PrimeService** dans Visual Studio Code.

1. Ouvrez la vue Explorateur de solutions dans Visual Studio Code.

    La vue Explorateur de solutions est accessible à partir du panneau barre latérale de Visual Studio Code. L’Explorateur de solutions est semblable à la vue Explorateur, mais elle est spécialement conçue pour fonctionner avec des projets Visual Studio Code plutôt qu’avec des systèmes de fichiers généraux.

1. Dans la vue Explorateur de solutions, cliquez avec le bouton droit sur **APL2007M4PrimeService**, puis sélectionnez **Nouveau projet**.

    Si vous ne voyez pas l’option **Nouveau projet**, assurez-vous de travailler dans l’affichage *Explorateur de solutions*, pas dans l’Affichage *Explorateur*.

1. Lorsque la liste des types de projet s’affiche, sélectionnez **Projet de test xUnit**.

1. Pour le nom du projet, tapez **PrimeService.UnitTests**, puis appuyez sur Entrer.

    Le nom du projet doit refléter le nom de la classe que vous testez et il doit être unique dans la solution. Dans ce cas, la classe est nommée `PrimeService`, de sorte que le projet de test est nommé `PrimeService.UnitTests`.

1. Sélectionnez l’emplacement du répertoire par défaut.

    Vous pouvez également créer le projet de test xUnit à l’aide du terminal Visual Studio Code. Ouvrez un terminal, accédez au dossier Nombres, puis exécutez la commande suivante :

    ```plaintext
    dotnet new xunit -n PrimeService.UnitTests
    ```

1. Sélectionnez **Créer un projet**, puis développez le dossier PrimeService.UnitTests.

1. Supprimez le fichier UnitTest1.cs créé avec le projet PrimeService.UnitTests.

    Avant de créer un test unitaire, vous devez ajouter une référence au projet de test unitaire qui pointe vers le projet de classe que vous souhaitez tester.

1. Pour ajouter une référence à votre projet de code, cliquez avec le bouton droit sur **PrimeService.UnitTests**, sélectionnez **Ajouter une référence de projet**, puis **Nombres**.

1. Pour créer une classe pour vos tests unitaires, cliquez avec le bouton droit sur **PrimeService.UnitTests**, sélectionnez **Nouveau fichier**, sélectionnez **Classe**, tapez **PrimeServiceTests** puis appuyez sur Entrée.

    Visual Studio Code doit ouvrir le fichier PrimeServiceTests.cs pour vous.

1. Prenez une minute pour examiner le fichier PrimeServiceTests.cs.

    Votre fichier doit être similaire à l’extrait de code suivant :

    ```csharp

    namespace PrimeService.UnitTests;
    public class PrimeServiceTests
    {
    }

    ```

1. Pour éviter les problèmes d’espace de noms lorsque vous générez le projet, mettez à jour le fichier PrimeServiceTests.cs comme suit :

    ```csharp

    namespace System.Numbers.UnitTests;
    public class PrimeServiceTests
    {
    }

    ```

    Un espace de noms en C# est utilisé pour organiser les classes et les types associés. Il s’agit d’un moyen d’éviter les collisions de noms et de faciliter la compréhension de l’organisation du code. Le suffixe `.UnitTests` dans l’espace de noms du projet de test est une convention commune pour indiquer que le code de cet espace de noms teste le code dans l’espace de noms System.Numbers. Cela permet de déterminer clairement, dans la structure du projet, le code de production et le code de test.

1. Prenez une minute pour examiner le fichier PrimeService.UnitTests.csproj.

    Le fichier PrimeService.UnitTests.csproj doit inclure un `<ItemGroup>` qui contient les éléments suivants `<PackageReference />` :

    ```xml

    <PackageReference Include="coverlet.collector" Version="6.0.0" />
    <PackageReference Include="Microsoft.NET.Test.Sdk" Version="17.8.0" />
    <PackageReference Include="xunit" Version="2.5.3" />
    <PackageReference Include="xunit.runner.visualstudio" Version="2.5.3" />

    ```

    Ces références de package sont requises pour utiliser xUnit comme bibliothèque de tests et configurer l’exécuteur de test. Vous devriez également voir les éléments suivants `<ItemGroup>` dans le fichier PrimeService.UnitTests.csproj :

    ```xml

    <ItemGroup>
        <Using Include="Xunit" />
    </ItemGroup>
    <ItemGroup>
        <ProjectReference Include="..\Numbers\Numbers.csproj" />
    </ItemGroup>

    ```

    Ces éléments sont nécessaires pour référencer le projet Nombres et utiliser l’infrastructure de test xUnit.

1. Pour créer la solution, appuyez sur **Ctrl+Maj+B**, puis sélectionnez **dotnet: build**.

    Vous pouvez également créer la solution à l’aide d’une commande CLI .NET (dotnet build) ou en cliquant avec le bouton droit sur le nœud de la solution dans la vue Explorateur de solutions et en sélectionnant **Créer**.

    > [!NOTE]
    > Si vous rencontrez des **erreurs** de génération, corrigez-les avant de poursuivre la version de démonstration. Vous devez avoir une build réussie avant de continuer.

Vous êtes maintenant prêt à créer un test unitaire à l’aide de GitHub Copilot Chat.

### Créer des tests unitaires à l’aide de la vue Conversation

GitHub Copilot et GitHub Copilot Chat peuvent vous aider à générer des tests unitaires pour votre code en fournissant des suggestions basées sur le contexte de votre codebase. Vous pouvez utiliser GitHub Copilot Chat pour générer des tests unitaires pour des méthodes ou des classes spécifiques dans votre code.

Utilisez les étapes suivantes pour terminer cette section de la version de démonstration :

1. Dans la vue Explorateur de solutions, sous Numéros, ouvrez le fichier PrimeService.cs.

1. Sélectionnez la méthode **IsPrime**.

1. Ouvrez la vue Conversation.

1. Sélectionnez le bouton **Joindre le contexte**.

    Le bouton **Attacher le contexte** (icône en forme de trombone) est utilisé pour informer GitHub Copilot du contexte pertinent dans votre base de code. Le contexte supplémentaire aide GitHub Copilot Chat à fournir des suggestions plus précises. Dans ce cas, vous souhaitez que GitHub Copilot utilise votre fichier PrimeServiceTests.cs lors de la proposition de tests unitaires.

1. Dans la liste déroulante **Rechercher les pièces jointes**, dans la section **récemment ouverte**, sélectionnez **PrimeServiceTests.cs**.

    La liste déroulante **Rechercher des pièces jointes** fournit certaines options par défaut parmi lesquelles vous pouvez choisir. Il comprend également une liste des fichiers récemment ouverts. Le fichier PrimeServiceTests.cs doit être répertorié dans la section récemment ouverte.

    Les options de recherche de pièces jointes incluent

1. Sélectionnez à nouveau le bouton **Attacher le contexte**.

1. Dans la zone de texte Rechercher les pièces jointes, saisissez **PrimeService.Unit**, puis sélectionnez **PrimeService.UnitTests.csproj**.

    > [!NOTE]
    > Démontrez comment faire glisser un fichier depuis l’affichage Explorateur et le déposer dans l’affichage Conversation. Dans de nombreux cas, il s’agit d’un moyen plus rapide d’ajouter du contexte.

1. Notez que la vue Chat est mise à jour avec le contexte supplémentaire.

1. Dans la vue Chat, sélectionnez **/tests ajouter des tests unitaires pour mon code**.

    L'option **/tests ajouter des tests unitaires pour mon code** est utilisée pour générer des tests unitaires pour le code que vous avez sélectionné dans l'éditeur. Dans ce cas, vous avez sélectionné la méthode **IsPrime** dans le fichier PrimeService.cs.

1. Prenez une minute pour consulter les suggestions de GitHub Copilot.

    La suggestion de GitHub Copilot comprend deux sections, un « Plan » et un exemple de code contenant des tests unitaires.

    Le plan suggère de créer un nouveau fichier PrimeServiceTest.cs pour les tests unitaires. Il suggère également de créer le fichier dans le dossier du projet Numbers.

1. Dans la vue Chat, sélectionnez **Appliquer les modifications**.

1. Notez que le bouton Appliquer les modifications place le code de test unitaire sur un nouvel onglet dans l'éditeur.

    Vous pouvez utiliser ce code pour mettre à jour le fichier PrimeServiceTests.cs dans votre projet PrimeService.UnitTests.

1. Dans le menu **Fichier**, sélectionnez **Enregistrer** sous, puis accédez au dossier PrimeService.UnitTests.

1. Sélectionnez **PrimeServiceTests.cs**, puis sélectionnez **Enregistrer**.

1. Lorsque vous êtes invité à écraser le fichier existant, sélectionnez **Oui**.

1. Prenez une minute pour examiner le fichier PrimeServiceTests.cs mis à jour.

    Le code suggéré par GitHub Copilot Chat doit inclure des tests pour des nombres premiers et non premiers spécifiques. Le code suggéré peut inclure des tests paramétrés (utilisant des attributs `[Theory]` et `[InlineData]`) pour tester plusieurs ensembles de données de manière plus concise.

    L’extrait de code fourni doit être similaire à l’extrait de code suivant :

    ```csharp

    using Xunit;
    namespace System.Numbers.UnitTests
    {
        public class PrimeServiceTests
        {
            private readonly PrimeService _primeService;
            public PrimeServiceTests()
            {
                _primeService = new PrimeService();
            }
            [Fact]
            public void IsPrime_InputIs1_ReturnsFalse()
            {
                var result = _primeService.IsPrime(1);
                Assert.False(result, "1 should not be prime");
            }
            [Fact]
            public void IsPrime_InputIs2_ReturnsTrue()
            {
                var result = _primeService.IsPrime(2);
                Assert.True(result, "2 should be prime");
            }
            [Fact]
            public void IsPrime_InputIs3_ReturnsTrue()
            {
                var result = _primeService.IsPrime(3);
                Assert.True(result, "3 should be prime");
            }
            [Fact]
            public void IsPrime_InputIs4_ReturnsFalse()
            {
                var result = _primeService.IsPrime(4);
                Assert.False(result, "4 should not be prime");
            }
            [Theory]
            [InlineData(5, true)]
            [InlineData(6, false)]
            [InlineData(7, true)]
            [InlineData(8, false)]
            [InlineData(9, false)]
            [InlineData(10, false)]
            public void IsPrime_Values_ReturnExpectedResult(int value, bool expected)
            {
                var result = _primeService.IsPrime(value);
                Assert.Equal(expected, result);
            }
        }
    }

    ```

    Remarquez que les tests unitaires nécessitent une instance de la classe PrimeService.

    ```csharp

    private readonly PrimeService _primeService;
    public PrimeServiceTests()
    {
        _primeService = new PrimeService();
    }

    ```

1. Recréez la solution.

    Vous devriez voir des « flèches de test » vertes à côté de chaque test unitaire si la construction est réussie.

    Vous allez créer d’autres tests unitaires dans la section suivante. Il n’est donc pas nécessaire de les exécuter pour l’instant.

    Toutefois, plusieurs façons d’exécuter le code figurant dans vos tests existent. Par exemple :

    - Vous pouvez exécuter les tests à partir du terminal Visual Studio Code à l’aide de la commande `dotnet test`.
    - Vous pouvez exécuter les tests à partir de la vue Explorateur de tests Visual Studio Code.
    - Vous pouvez exécuter les tests à partir de la palette de commandes Visual Studio Code à l’aide de la commande **Test : Exécuter tous les tests**.
    - Vous pouvez exécuter les tests à partir de l’éditeur Visual Studio Code en sélectionnant l’option **Exécuter les tests dans le fichier actuel** dans le menu contextuel.

    Les tests que vous avez créés pendant cette section de la version de démonstration doivent s’exécuter correctement. Les « flèches de test » vertes en regard du test unitaire deviennent des cercles verts avec une coche.

### Créer des tests unitaires à l’aide d’une conversation inline

Utilisez les étapes suivantes pour terminer cette section de la version de démonstration :

1. Dans la vue Explorateur de solutions, ouvrez le fichier PrimeService.cs.

    PrimeService.cs se trouve dans le dossier Nombres.

1. Sélectionnez la méthode IsPrime.

1. Ouvrez une session de conversation inline, puis entrez l’invite suivante :

    ```plaintext
    Create unit tests for the IsPrime method using the xUnit framework.
    ```

1. Prenez une minute pour passer en revue les suggestions fournies par la conversation inline.

    ```csharp

    using Xunit;
    namespace System.Numbers.UnitTests
    {
        public class PrimeServiceTests
        {
            private readonly PrimeService _primeService;
            public PrimeServiceTests()
            {
                _primeService = new PrimeService();
            }
            [Fact]
            public void IsPrime_InputIs1_ReturnsFalse()
            {
                var result = _primeService.IsPrime(1);
                Assert.False(result, "1 should not be prime");
            }
            [Fact]
            public void IsPrime_InputIs2_ReturnsTrue()
            {
                var result = _primeService.IsPrime(2);
                Assert.True(result, "2 should be prime");
            }
            [Fact]
            public void IsPrime_InputIs3_ReturnsTrue()
            {
                var result = _primeService.IsPrime(3);
                Assert.True(result, "3 should be prime");
            }
            [Fact]
            public void IsPrime_InputIs4_ReturnsFalse()
            {
                var result = _primeService.IsPrime(4);
                Assert.False(result, "4 should not be prime");
            }
            [Theory]
            [InlineData(5, true)]
            [InlineData(6, false)]
            [InlineData(7, true)]
            [InlineData(8, false)]
            [InlineData(9, false)]
            [InlineData(10, false)]
            public void IsPrime_Values_ReturnExpectedResult(int value, bool expected)
            {
                var result = _primeService.IsPrime(value);
                Assert.Equal(expected, result);
            }
        }
    }

    ```

1. Notez que la vue Chat et le chat en ligne produisent une couverture de test similaire.

1. Pour ignorer la suggestion de chat en ligne, sélectionnez **Supprimer**, puis fermez l’onglet de fichier créé par le chat en ligne.

    N’oubliez pas que les tests unitaires proposés par GitHub Copilot pendant cette version de démonstration peuvent être incomplets. La version de démonstration suivante examine d’autres cas d’arête que vous pouvez envisager de tester.

### Résumé

Dans cette version de démonstration, vous avez créé des tests unitaires pour un projet de code à l’aide de GitHub Copilot Chat dans Visual Studio Code. Vous avez créé un projet de test xUnit, ajouté une référence au projet que vous souhaitez tester et généré des tests unitaires pour la méthode `IsPrime` dans la classe `PrimeService`. Vous avez utilisé GitHub Copilot Chat pour générer des tests unitaires dans la vue Conversation et la conversation inline.
