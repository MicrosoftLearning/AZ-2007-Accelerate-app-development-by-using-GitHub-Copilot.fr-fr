---
demo:
  title: "Démonstration\_: Créer des tests unitaires pour des conditions spécifiques à l’aide de GitHub Copilot"
  module: 'Module 4: Develop unit tests using GitHub Copilot tools'
---

# Démonstration : Créer des tests unitaires pour des conditions spécifiques à l’aide de GitHub Copilot

## Instructions

Les activités de la version de démonstration sont conçues pour un environnement qui inclut les ressources suivantes :

- Visual Studio Code.
- L’extension du kit de développement C# pour Visual Studio Code.
- Les extensions GitHub Copilot et GitHub Copilot Chat pour Visual Studio Code. Il est nécessaire de disposer d’un compte GitHub avec un abonnement actif pour GitHub Copilot.
- Des exemples de projets de code créés en C#.

**REMARQUE** : Nous recommandons aux instructeurs d’utiliser leur propre compte GitHub et leur abonnement GitHub Copilot pour les démonstrations. Ainsi vous pouvez contrôler et personnaliser votre environnement de développement. Cette démarche facilite également l’ajustement des démonstrations en fonction des besoins de vos salles de classe.

**IMPORTANT** : Si vous choisissez d’exécuter les démonstrations dans l’environnement de laboratoire hébergé plutôt que sur votre ordinateur personnel instructeur, vous pouvez décompresser les exemples d’applications dans l’environnement hébergé. Vous devez configurer les extensions GitHub Copilot dans l’environnement hébergé avant de pouvoir exécuter les démonstrations. Vous pouvez constater que l’environnement hébergé est plus lent que votre environnement local. Vous devrez probablement ajuster l’allure des démonstrations en conséquence.

### Présentez la version de démonstration

Les extensions GitHub Copilot peuvent vous aider à créer des tests unitaires pour des conditions spécifiques dans votre code. Par exemple, vous pouvez utiliser GitHub Copilot Chat pour tester le comportement d’une méthode lorsqu’elle reçoit une entrée spécifique.

Dans cette version de démonstration, vous utilisez les extensions GitHub Copilot pour créer des tests unitaires pour des conditions spécifiques.

### Créer des tests unitaires à l’aide de GitHub Copilot

Vous pouvez créer des tests unitaires à l’aide de suggestions d’autocomplétion GitHub Copilot. L’utilisation des suggestions d’autocomplétion peut vous aider à générer rapidement des tests unitaires pour votre code.

Dans cette section de la version de démonstration, vous utilisez GitHub Copilot pour créer des tests unitaires pour la méthode `IsPrime` de la classe `PrimeService`.

Utilisez les étapes suivantes pour terminer cette section de la version de démonstration :

1. Ouvrez le dossier de projet **APL2007M4PrimeService-UnitTests** dans Visual Studio Code.

1. Ouvrez le fichier PrimeServiceTests.cs dans l’éditeur.

1. Supprimez tout le code dans la classe `PrimeServiceTests`.

    Le contenu du fichier PrimeServiceTests.cs doit ressembler à l’extrait de code suivant :

    ```csharp

    namespace System.Numbers.UnitTests;
    public class PrimeServiceTests
    {
    }

    ```

1. Enregistrez le fichier PrimeServiceTests.cs, puis régénérez la solution.

1. Pour que GitHub Copilot génère une saisie semi-automatique inlined, créez une ligne vide à l’intérieur de la classe `PrimeServiceTests`.

    Si vous attendez une seconde ou deux, GitHub Copilot vous suggère une saisie semi-automatique pour la classe `PrimeServiceTests`.

1. Sélectionnez **Accepter**, puis prenez un moment pour examiner les tests unitaires générés par GitHub Copilot.

1. Prenez une minute pour examiner la collection de tests unitaires générés par GitHub Copilot pour la méthode `IsPrime`.

    La section suivante de la version de démonstration montre comment utiliser GitHub Copilot Chat pour demander à GitHub Copilot de suggérer des cas d’arête supplémentaires qui doivent être testés.

    ```csharp

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
            public void IsPrime_ReturnsFalse_ForNegativeNumbers()
            {
                // Arrange
                int candidate = -5;
                // Act
                bool result = _primeService.IsPrime(candidate);
                // Assert
                Assert.False(result);
            }
            [Fact]
            public void IsPrime_ReturnsFalse_ForZero()
            {
                // Arrange
                int candidate = 0;
                // Act
                bool result = _primeService.IsPrime(candidate);
                // Assert
                Assert.False(result);
            }
            [Fact]
            public void IsPrime_ReturnsFalse_ForOne()
            {
                // Arrange
                int candidate = 1;
                // Act
                bool result = _primeService.IsPrime(candidate);
                // Assert
                Assert.False(result);
            }
            [Fact]
            public void IsPrime_ReturnsTrue_ForPrimeNumbers()
            {
                // Arrange
                int candidate = 7;
                // Act
                bool result = _primeService.IsPrime(candidate);
                // Assert
                Assert.True(result);
            }
        }
    }

    ```

### Créer des tests unitaires pour des conditions spécifiques à l’aide de GitHub Copilot et de GitHub Copilot Chat

1. Sélectionnez le contenu de la classe `PrimeServiceTests`.

1. Ouvrez la vue Conversation.

1. Pour ajouter le fichier PrimeService.cs au contexte de la vue Conversation, faites glisser-déplacer le fichier PrimeService.cs de la vue Explorateur dans la vue Conversation.

1. Entrez le prompt suivant dans la vue Conversation :

    ```plaintext
    @workspace #selection are there any edge cases that should also be tested 
    ```

1. Prenez un moment pour examiner les suggestions fournies par GitHub Copilot.

    ```plaintext
    Yes, there are a few edge cases that should also be tested:
    
    1. Large Prime Numbers: Ensure the function can handle large prime numbers.

    2. Large Non-Prime Numbers: Ensure the function can handle large non-prime numbers.

    3. Even Numbers Greater Than 2: Ensure the function returns false for even numbers greater than 2.

    4. Small Prime Numbers: Ensure the function correctly identifies small prime numbers like 2 and 3.

    Here are the additional test cases:
    ```

    ```csharp

    [Fact]
    public void IsPrime_ReturnsTrue_ForTwo()
    {
        // Arrange
        int candidate = 2;
        // Act
        bool result = _primeService.IsPrime(candidate);
        // Assert
        Assert.True(result);
    }
    [Fact]
    public void IsPrime_ReturnsTrue_ForThree()
    {
        // Arrange
        int candidate = 3;
        // Act
        bool result = _primeService.IsPrime(candidate);
        // Assert
        Assert.True(result);
    }
    [Fact]
    public void IsPrime_ReturnsFalse_ForEvenNumbersGreaterThanTwo()
    {
        // Arrange
        int candidate = 4;
        // Act
        bool result = _primeService.IsPrime(candidate);
        // Assert
        Assert.False(result);
    }
    [Fact]
    public void IsPrime_ReturnsTrue_ForLargePrimeNumber()
    {
        // Arrange
        int candidate = 7919;
        // Act
        bool result = _primeService.IsPrime(candidate);
        // Assert
        Assert.True(result);
    }
    [Fact]
    public void IsPrime_ReturnsFalse_ForLargeNonPrimeNumber()
    {
        // Arrange
        int candidate = 8000;
        // Act
        bool result = _primeService.IsPrime(candidate);
        // Assert
        Assert.False(result);
    }

    ```

1. Créez une ligne vide après la dernière méthode de test dans la classe `PrimeServiceTests`.

1. Dans la vue Conversation, pointer avec la souris sur l’extrait de code, puis sélectionnez **Insérer au niveau du curseur**.

1. Enregistrez le fichier PrimeServiceTests.cs, puis régénérez la solution.

1. Prenez une minute pour examiner la collection de tests unitaires générés par GitHub Copilot pour la méthode `IsPrime`.

    Comme toujours, il est important d’examiner le travail effectué par GitHub Copilot pour vous assurer que les tests sont valides et qu’ils couvrent les cas de périphérie que vous souhaitez tester. Une fois que vous êtes satisfait des tests, vous pouvez les exécuter pour vérifier leur réussite.

1. Placez le pointeur de la souris sur l’une des « flèches de test » vertes.

    Notez que le message d’info-bulle vous indique que vous pouvez cliquer pour exécuter le test ou faites un clic droit pour afficher plus d’options.

1. Faites un clic droit sur l’une des « flèches de test » vertes.

1. Sélectionnez **Révéler dans l'Explorateur de tests**.

    Notez que la vue Explorateur de tests s’ouvre. La vue Explorateur de tests peut être utilisée pour exécuter et déboguer des tests, ainsi que pour afficher les résultats des séries de tests. Pour ouvrir la vue Explorateur de tests manuellement, sélectionnez **Tester** à partir de la barre d’activité sur le côté gauche de la fenêtre Visual Studio Code. L’icône de la vue **Tester** est celle qui ressemble à un flacon de laboratoire.

1. En haut de la vue Explorateur de tests, sélectionnez **Exécuter des tests**.

    Après quelques secondes, l’Explorateur de tests affiche les résultats de la série de tests. Vous constaterez la réussite de tous les tests. Des coches vertes dans l’Explorateur de tests et à gauche des tests unitaires dans l’Éditeur indiquent que le test a réussi.

### Résumé

Dans cette version de démonstration, vous avez utilisé GitHub Copilot et GitHub Copilot Chat pour créer des tests unitaires correspondant à des conditions spécifiques dans la classe `PrimeService`. Vous avez utilisé des saisies semi-automatiques de ligne de code pour générer des assertions afin de vous assurer que les paramètres d’entrée de fonction sont valides et vous avez utilisé la vue Conversation pour demander à GitHub Copilot de suggérer des cas de périphérie supplémentaires qui doivent être testés. Vous avez examiné les suggestions fournies par GitHub Copilot et exécuté les tests pour vérifier leur réussite. Vous avez également appris à utiliser l’Explorateur de tests dans Visual Studio Code pour exécuter et afficher les résultats des séries de tests.
