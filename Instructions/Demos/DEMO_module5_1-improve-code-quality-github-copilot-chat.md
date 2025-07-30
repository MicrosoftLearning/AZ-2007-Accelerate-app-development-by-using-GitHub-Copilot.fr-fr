---
demo:
  title: "Démonstration\_: Améliorer la qualité du code à l’aide de GitHub Copilot Chat"
  module: 'Module 5: Implement code improvements using GitHub Copilot tools'
---

# Démonstration : Améliorer la qualité du code à l’aide de GitHub Copilot Chat

## Instructions

Les activités de la version de démonstration sont conçues pour un environnement qui inclut les ressources suivantes :

- Visual Studio Code.
- L’extension du kit de développement C# pour Visual Studio Code.
- Les extensions GitHub Copilot et GitHub Copilot Chat pour Visual Studio Code. Il est nécessaire de disposer d’un compte GitHub avec un abonnement actif pour GitHub Copilot.
- Des exemples de projets de code créés en C#.

**REMARQUE** : Nous recommandons aux instructeurs d’utiliser leur propre compte GitHub et leur abonnement GitHub Copilot pour les démonstrations. Ainsi vous pouvez contrôler et personnaliser votre environnement de développement. Cette démarche facilite également l’ajustement des démonstrations en fonction des besoins de vos salles de classe.

**IMPORTANT** : Si vous choisissez d’exécuter les démonstrations dans l’environnement de laboratoire hébergé plutôt que sur votre ordinateur personnel instructeur, vous pouvez décompresser les exemples d’applications dans l’environnement hébergé. Vous devez configurer les extensions GitHub Copilot dans l’environnement hébergé avant de pouvoir exécuter les démonstrations. Vous pouvez constater que l’environnement hébergé est plus lent que votre environnement local. Vous devrez probablement ajuster l’allure des démonstrations en conséquence.

### Présentez la version de démonstration

Le terme « qualité du code » fait référence à la qualité globale de la base de code, notamment la lisibilité, la maintenance et la modularité. La qualité du code est une mesure de la façon dont votre code est « bien structuré » et de sa facilité de compréhension, de maintenance et d’extension.

> [!IMPORTANT]
> Expliquez aux étudiants que cette version de démonstration ne concerne pas les meilleures pratiques de développement de code de haute qualité. Il se concentre plutôt sur l’utilisation de GitHub Copilot Chat pour générer des suggestions d’amélioration de la qualité du code dans un exemple d’application. Les suggestions ne représentent pas les meilleures pratiques ou des solutions complètes pour développer un code de haute qualité. Les développeurs doivent faire appel à leur bon sens et à leur expertise pour évaluer et mettre en œuvre les suggestions fournies par GitHub Copilot Chat. L’adoption des recommandations de GitHub Copilot ne remplace en aucun cas les processus de révision et de tests de code approfondis.

Les sections suivantes fournissent une vue d’ensemble de la refactorisation du code et de la qualité du code, des notions que vos étudiants doivent connaître.

#### Refactorisation du code et code de haute qualité

La refactorisation du code est le processus de restructuration du code existant sans modifier son comportement externe. L’objectif de la refactorisation du code est d’améliorer la structure interne du codebase, ce qui facilite la compréhension, la maintenance et l’extension. La refactorisation du code peut vous aider à produire du code de haute qualité en améliorant la lisibilité, en réduisant la complexité, en améliorant la modularité et en augmentant la réutilisation. Chacun de ces facteurs permet de créer une base de code plus gérable.

Les développeurs doivent considérer les facteurs suivants pour améliorer la qualité du code :

- Lisibilité : Améliorer ou renforcer la lisibilité du code peut faciliter la compréhension des développeurs.
- Complexité : Réduire la complexité du code facilite la compréhension, la gestion et la maintenance du code.
- Réutilisation et modularité : La décomposition du code en modules ou composants plus petits et réutilisables peut faciliter la gestion et la maintenance du code.

Les facteurs énumérés ci-dessus représentent trois domaines communs que les développeurs identifient lorsqu’ils discutent de la qualité du code. Voici d’autres facteurs qui peuvent être associés à la qualité du code :

- Testabilité : Facilité avec laquelle le code peut être testé pour s’assurer qu’il fonctionne correctement. Souvent un produit de conception et de modularité.
- Extensibilité : Facilité avec laquelle le code peut être étendu ou amélioré pour ajouter de nouvelles fonctionnalités ou fonctionnalités. Souvent un produit de conception et de modularité.

La qualité du code n’est pas le seul facteur que les développeurs considèrent pendant les révisions de code. Voici d’autres facteurs que les développeurs évaluent souvent en plus de la qualité du code :

- Fiabilité : La capacité du code à réaliser les fonctions prévues dans les conditions spécifiées.
- Performances : Comment le code s’exécute efficacement.
- Sécurité : Capacité du code à protéger les données et les ressources contre l’accès ou la modification non autorisés.
- Scalabilité : Capacité du code à gérer des charges de travail ou une croissance accrues à l’avenir.
- Convivialité : Facilité d’utilisation du code par les développeurs ou les utilisateurs finaux.
- Portabilité : Capacité du code à s’exécuter sur différentes plateformes ou environnements.

> [!NOTE]
> Les deux unités suivantes de ce module couvrent l’amélioration de la fiabilité, du niveau de performance et de la sécurité du code à l’aide de GitHub Copilot Chat.

L’amélioration de la qualité du code est souvent considérée comme un précurseur de l’ajout de nouvelles fonctionnalités ou améliorations. Vous devez envisager des améliorations de la qualité du code avant de travailler sur la fiabilité, le niveau de performance ou la sécurité du code.

Dans cette version de démonstration, vous allez utiliser GitHub Copilot Chat pour générer des suggestions qui vous aideront à améliorer la qualité du code dans un exemple d’application.

### Développer des prompts pour GitHub Copilot Chat

Soulignez à nouveau l’importance de rédiger des requêtes efficaces.

Les prompts que vous écrivez pour GitHub Copilot Chat doivent fournir un *contexte* et une *intention* clairement définis. L’*intention* partie de l’invite décrit l’objectif à atteindre. Par exemple, vous pouvez demander à GitHub Copilot de « refactoriser pour améliorer la modularité du code ». La partie du *contexte* de l’invite indique à GitHub Copilot quelles ressources prendre en compte. Par exemple, vous pouvez souhaiter que GitHub Copilot prenne en compte l’ensemble de l’espace de travail, mais qu’il se concentre sur un fichier ou une section de code spécifique. Tenez compte des suggestions suivantes lors du développement de vos invites :

- Définissez un contexte externe délimité à un niveau supérieur au code que vous souhaitez mettre à jour. Par exemple, si vous souhaitez refactoriser une méthode, spécifiez la classe ou le fichier qui contient la méthode comme contexte externe. Repérez la méthode comme contexte interne.
- Utilisez les participants de conversation et les variables de conversation pour vous aider à spécifier le contexte. Vous pouvez utiliser les variables de conversation `#file:` et `#selection` pour identifier le code spécifique sur lequel vous vous concentrez. Vous pouvez également inclure l’espace de travail complet (`@workspace`) le cas échéant. Supposons que vous souhaitez refactoriser une méthode dans un fichier spécifique. Vous pouvez utiliser la variable de conversation `#file:` pour indiquer à GitHub Copilot quel fichier examiner. Vous pouvez sélectionner la méthode dans l’éditeur et utiliser la variable de conversation `#selection` pour indiquer à GitHub Copilot quel code vous souhaitez refactoriser. Vous pouvez également utiliser la variable de conversation `@workspace` pour indiquer à GitHub Copilot de prendre en compte l’ensemble de l’espace de travail. Renforcez le contexte spécifié en faisant référence à la sélection ou au fichier dans la partie en langage naturel de votre invite. Par exemple, vous pouvez dire : « comment puis-je améliorer la lisibilité du code sélectionné ? »
- L’intention doit être claire et spécifique et spécifier l’aspect de qualité du code que vous souhaitez améliorer. Par exemple, vous pouvez demander à GitHub Copilot Chat de « Comment améliorer la modularité du code sélectionné ».

Pendant cette phase de la version de démonstration, vous passez en revue le projet **APL2007M5BankAccount**, puis vous créez trois requêtes pour GitHub Copilot Chat. Les invites se concentrent sur l’amélioration de la lisibilité, de la maintenance et de la modularité du code.

Suivez les étapes ci-dessous pour effectuer cette phase de la version de démonstration :

1. Ouvrez l’exemple d’application **APL2007M5BankAccount** dans Visual Studio Code.

1. Ouvrez le fichier **Program.cs** et évaluez le code.

    Ce programme est une application console qui simule un système bancaire. Voici les fonctionnalités clés :

    - Méthode principale : La méthode principale est le point d’entrée de l’application. Cela crée des comptes bancaires et utilise les comptes pour simuler des transactions.

    - Constantes : Le programme définit plusieurs constantes en haut de la classe Program. Les constantes incluent des éléments tels que : le nombre de comptes à créer, le nombre de transactions à simuler et les limites des transactions.

1. Prenez une minute pour écrire des invites que vous pouvez utiliser pour améliorer la lisibilité du code, la maintenance et la modularité.

    Pour le projet BankAccount, vous devez attacher le fichier BankAccount.cs et/ou le fichier Program.cs au contexte Conversation. Vos requêtes pourraient être similaires à l’exemple suivant :

    Invite : `@workspace /explain How can I improve the readability of the [selected code]?`

    Invite : `@workspace /explain #selection How can I improve the maintainability of the [selected code]?`

    Invite : `@workspace /explainHow can I improve the modularity of the [selected code]?`

    Invite : `#selection How can I refactor the [selected code] to improve modularity?`

    Invite : `@workspace /explain What are some options for simplifying the [selected code]?`

1. Créez trois requêtes à utiliser pour le reste de la version de démonstration.

### Refactorisez votre code en utilisant GitHub Copilot Chat

Vous pouvez utiliser GitHub Copilot Chat pour suggérer des mises à jour de code qui refactorisent et améliorent votre code. Il est important de comprendre votre code et vos objectifs avant de prendre une décision sur la façon de refactoriser l’application.

Les suggestions que GitHub Copilot Chat fournit doivent être examinées attentivement. Prenez en compte les suggestions qui prennent en charge vos objectifs avant de les implémenter. Dans le cadre de cette version de démonstration, votre temps peut également être un facteur de choix des suggestions à implémenter.

Suivez les étapes ci-dessous pour effectuer cette phase de la version de démonstration :

1. Prenez quelques instants pour évaluer les méthodes incluses dans le fichier Program.cs.

    - Méthode CreateBankAccounts : Cette méthode crée un nombre spécifié de comptes bancaires avec des soldes initiaux, des noms de titulaires de comptes, des types de comptes et des dates d’ouverture aléatoires. Elle utilise un bloc try-catch pour gérer les exceptions qui peuvent se produire lors de la création du compte.

    - Méthode SimulateTransactions : Cette méthode simule un nombre spécifié de transactions sur une liste de comptes bancaires. Elle génère un montant de transaction aléatoire pour chaque transaction, puis crédite ou débite le compte de ce montant, selon que le montant est positif ou négatif. Elle utilise un bloc try-catch pour gérer les exceptions qui pourraient survenir au cours des transactions.

    - Méthode SimulateTransfers : Cette méthode est identique à la méthode SimulateTransactions. Elle semble être destinée à simuler des transferts entre comptes, mais actuellement,elle simule simplement les transactions sur des comptes individuels.

    - Méthode GenerateRandomDollarAmount : Cette méthode génère un montant de dollar aléatoire dans une plage spécifiée. Elle utilise une formule différente pour générer le montant selon que le montant est pour un solde de compte ou une transaction.

    - Méthode GenerateRandomAccountHolder : Cette méthode sélectionne un nom de titulaire de compte aléatoire dans une liste prédéfinie de noms.

    - Méthode GenerateRandomAccountType : Cette méthode sélectionne un type de compte aléatoire à partir d’une liste prédéfinie de types.

    - Méthode GenerateRandomDateOpened : Cette méthode génère une date aléatoire dans une plage spécifiée d’années à partir de la date actuelle.

1. Vérifiez que le projet génère et s’exécute sans erreur.

1. Choisissez votre première invite dans les invites que vous avez préparées.

1. Sélectionnez le code que vous souhaitez améliorer, puis ouvrez la vue Conversation.

1. Dans la vue Conversation, utilisez le bouton **Attacher le contexte** pour ajouter les fichiers appropriés au contexte Conversation, puis entrez votre requête.

    Vous pouvez également illustrer l’utilisation d’une opération de glisser-déplacer pour joindre des fichiers à partir de la vue Explorateur de solutions au contexte de conversation.

1. Vérifiez les suggestions fournies par GitHub Copilot Chat.

    Par exemple, supposons que vous effectuiez les actions suivantes :

    - Vous décidez de travailler sur le fichier Program.cs.
    - Vous choisissez l’invite suivante : `@workspace /explain #selection How can I improve the readability of the GenerateRandomBalance, GenerateRandomAccountHolder, GenerateRandomAccountType, and GenerateRandomDateOpened methods?`
    - Vous ouvrez le fichier Program.cs et sélectionnez les méthodes suivantes : `GenerateRandomBalance`, `GenerateRandomAccountHolder`, `GenerateRandomAccountType`, `GenerateRandomDateOpened`.
    - Vous ouvrez la vue Conversation et attachez le fichier Program.cs au contexte Conversation.
    - Vous entrez l’invite dans la vue Conversation.

    Une fois ces actions terminées, GitHub Copilot Chat suggère des mises à jour similaires à la réponse suivante :

    *Pour améliorer la lisibilité de ces méthodes, vous pouvez suivre ces étapes :*

    *1. Extraire le code redondant dans des méthodes distinctes : L’objet aléatoire est créé plusieurs fois dans différentes méthodes. Vous pouvez créer un objet aléatoire statique au niveau de la classe et l’utiliser dans toutes les méthodes. Cette approche permettrait non seulement d’améliorer la lisibilité, mais également de fournir une meilleure aléatoire.*

    `private static readonly Random random = new Random();`

    *2. Utilisez des noms de variables explicites : Le nom de la variable `range` dans la méthode GenerateRandomDateOpened manque de clarté. Un nom plus descriptif comme daysRange serait préférable.*

    *3. Ajoutez des commentaires : Bien que le code soit principalement explicite, l’ajout de commentaires pour expliquer ce que chaque méthode peut être utile pour d’autres développeurs lisant votre code.*

    *4. Utiliser des constantes à la place des valeurs magiques : Dans la méthode GenerateRandomDateOpened, le nombre `10` est utilisé pour représenter le nombre d’années en arrière de la date de début. Cette valeur pourrait être extraite dans une constante avec un nom explicite, comme `MaxYearsBack`.*

    *5. Utiliser le mot clé var : En C#, vous pouvez utiliser le mot clé var lorsque le côté droit de l’affectation rend le type évident. Cette approche peut rendre votre code plus clair et plus facile à lire.*

   *Voici comment votre code peut s’occuper de ces améliorations :*

    ```csharp

    private static readonly Random random = new Random();
    private const int MaxYearsBack = 10;
    static double GenerateRandomBalance(double min, double max)
    {
        double balance = random.NextDouble() * (max - min) + min;
        return Math.Round(balance, 2);
    }
    static string GenerateRandomAccountHolder()
    {
        string[] accountHolderNames = {  /* names here */  };
        var accountHolderName = accountHolderNames[random.Next(0, accountHolderNames.Length)];
        return accountHolderName;
    }
    static string GenerateRandomAccountType()
    {
        string[] accountTypes = {  /* types here */  };
        return accountTypes[random.Next(0, accountTypes.Length)];
    }
    static DateTime GenerateRandomDateOpened()
    {
        DateTime startDate = new DateTime(DateTime.Today.Year - MaxYearsBack, 1, 1);
        int daysRange = (DateTime.Today - startDate).Days;
        DateTime randomDate = startDate.AddDays(random.Next(daysRange));
        if (randomDate.Year == DateTime.Today.Year && randomDate >= DateTime.Today)
        {
            randomDate = randomDate.AddDays(-1);
        }
        return randomDate;
    }

    ```

    > [!IMPORTANT]
    > Notez les valeurs d’espace réservé (telles que `/* types here */`) dans les méthodes `GenerateRandomAccountHolder` et `GenerateRandomAccountType` . GitHub Copilot Chat remplace occasionnellement les détails du code par des espaces réservés. Ils sont faciles à repérer si vous faites attention. Vous devez remplacer les valeurs d’espace réservé par des valeurs de votre application lorsque vous implémentez une mise à jour. Si vous voyez des espaces réservés, vous devez effectuer une copie de votre code existant avant d’implémenter les mises à jour suggérées. Si le bloc de code suggéré s’aligne sur le code de votre application, vous pouvez utiliser un commentaire de bloc pour commenter votre code existant, puis utiliser le bouton **Insérer au curseur** pour implémenter les mises à jour suggérées sans créer de conflit d’affectation de noms. Une fois que vous avez vérifié que la mise à jour suggérée fonctionne comme prévu, vous pouvez supprimer le commentaire de bloc.

1. Implémentez les mises à jour suggérées qui aident à améliorer la lisibilité du code, la facilité de maintenance et la modularité.

    Si vous avez utilisé bloquer les commentaires pour commenter votre code existant, vous pouvez utiliser l’ **Insertion de l’affichage Conversation au curseur** pour insérer les mises à jour suggérées. Vous pouvez également utiliser l’option Copier et coller la mise à jour à l’emplacement de votre choix.

    Prenez en compte les normes de codage et les stratégies implémentées sur votre lieu de travail avant de choisir les suggestions de mise à jour à implémenter.

1. Pour vous assurer qu’aucune erreur n’a été introduite lorsque vous avez implémenté vos mises à jour, générez et exécutez votre solution avant de continuer.

1. Entrez votre deuxième invite et évaluez les mises à jour proposées par GitHub Copilot Chat.

1. Examinez les suggestions fournies par GitHub Copilot Chat.

    Par exemple, supposons que vous effectuiez les actions suivantes :

    - Vous implémentez les mises à jour suggérées par GitHub Copilot Chat pour le premier exemple d’invite.
    - Vous décidez de continuer à travailler sur le fichier Program.cs.
    - Vous choisissez l’invite suivante : `@workspace /explain How can I improve the maintainability of the Main, GenerateRandomBalance, GenerateRandomAccountHolder, GenerateRandomAccountType, and GenerateRandomDateOpened methods?`.
    - Vous sélectionnez la (les) méthode(s) suivante(s) : `Main`, `GenerateRandomBalance`, `GenerateRandomAccountHolder`, `GenerateRandomAccountType`, `GenerateRandomDateOpened`.
    - Vous ouvrez la vue Conversation et attachez le fichier Program.cs au contexte Conversation.
    - Vous entrez l’invite dans la vue Conversation.

    Une fois ces actions terminées, GitHub Copilot Chat suggère des mises à jour similaires à la réponse suivante :

    *Pour améliorer la facilité de maintenance de ces méthodes, vous pouvez suivre ces étapes :*

    *1. Séparer les responsabilités : La méthode principale réalise plusieurs actions : création de comptes, simulation de transactions, simulation de virements. Ces actions pourraient être réparties dans des méthodes distinctes afin d’améliorer la lisibilité et la facilité de maintenance.*

    *2. Gestion des erreurs : Le code utilise une exception générale pour la gestion des erreurs. Il serait préférable de créer des exceptions personnalisées, spécifiques à l’application. La compréhension et le traitement des erreurs s'en trouveraient facilités.*

    *3. Valeurs magiques : Le code contient des valeurs numériques codées en dur (par exemple 20 pour le nombre de comptes, 100 pour le nombre de transactions, etc.). Ces valeurs devraient être remplacées par des constantes nommées.*

    *4. Duplication de code : Le code de génération de valeurs aléatoires est dupliqué à plusieurs endroits. Il serait pertinent de le refactoriser dans une classe utilitaire ou des méthodes dédiées.*

    ```csharp

    class Program
    {
        private static readonly Random random = new Random();
        private const int MaxYearsBack = 10;
        private const int NumberOfAccounts = 20;
        private const int NumberOfTransactions = 100;
        static void Main(string[] args)
        {
            List<BankAccount> accounts = CreateBankAccounts(NumberOfAccounts);
            SimulateTransactions(accounts, NumberOfTransactions);
            SimulateTransfers(accounts);
        }
        static List<BankAccount> CreateBankAccounts(int numberOfAccounts)
        {
            List<BankAccount> accounts = new List<BankAccount>();
            int createdAccounts = 0;
            while (createdAccounts < numberOfAccounts)
            {
                try
                {
                    // same code as before...
                }
                catch (Exception ex)
                {
                    Console.WriteLine($"Account creation failed: {ex.Message}");
                }
            }
            return accounts;
        }
        static void SimulateTransactions(List<BankAccount> accounts, int numberOfTransactions)
        {
            // same code as before...
        }
        static void SimulateTransfers(List<BankAccount> accounts)
        {
            // same code as before...
        }
        // same helper methods as before...
    }

    ```

1. Examinez les suggestions fournies par GitHub Copilot Chat.

1. Implémentez les mises à jour suggérées qui aident à améliorer la lisibilité du code, la facilité de maintenance et la modularité.

    Si vous avez utilisé bloquer les commentaires pour commenter votre code existant, vous pouvez utiliser l’ **Insertion de l’affichage Conversation au curseur** pour insérer les mises à jour suggérées. Vous pouvez également utiliser l’option Copier et coller la mise à jour à l’emplacement de votre choix.

1. Pour vous assurer qu’aucune erreur n’a été introduite par les modifications, compilez et exécutez votre solution avant de continuer.

1. Entrez votre troisième invite, puis prenez une minute pour évaluer les suggestions.

    Par exemple, supposons que vous effectuiez les actions suivantes :

    - Vous mettez en œuvre les mises à jour suggérées par GitHub Copilot Chat pour les première et deuxième requêtes.
    - Vous décidez de continuer à travailler sur le fichier Program.cs.
    - Vous choisissez l’invite suivante : `@workspace /explain How can I improve the modularity of the Program.cs file?`.
    - Vous sélectionnez le code suivant : Sélectionnez tout le fichier Program.cs.
    - Vous ouvrez la vue Conversation et attachez le fichier Program.cs au contexte Conversation.
    - Vous entrez l’invite dans la vue Conversation.

    Une fois ces actions terminées, GitHub Copilot Chat suggère des mises à jour similaires à la réponse suivante :

    *Pour améliorer la modularité du fichier Program.cs, vous pouvez suivre les étapes suivantes :*

    *1. Préoccupations distinctes : La classe `Program` prend en charge trop de fonctions à la fois. Elle crée des comptes, simule des transactions et génère des données aléatoires. Chacune de ces responsabilités devrait être confiée à une classe distincte. Par exemple, vous pourriez créer une classe `BankAccountFactory` dédiée à la création de comptes bancaires, une classe `TransactionSimulator` pour la simulation de transactions, et une classe `RandomDataGenerator` pour la génération de données aléatoires.*

    *2. Utiliser des interfaces : Les interfaces permettent de définir un contrat pour les classes. Votre code peut ainsi être plus flexible et plus facile à tester. Par exemple, vous pouvez définir une interface `IAccountFactory` avec une méthode `Create`, puis faire en sorte que `BankAccountFactory` implémente cette interface.*

    *3. Valeurs magiques : Plusieurs « valeurs magiques » apparaissent dans le code (comme 10, 50000, -500, 500, etc.). Ces valeurs doivent être remplacées par des constantes nommées pour améliorer la lisibilité et la maintenabilité du code.*

    *4. Duplication : Les méthodes `SimulateTransactions` et `SimulateTransfers` contiennent quasiment le même code. Cette duplication peut être éliminée en créant une méthode commune que les deux méthodes appellent.*

   *Voici un exemple de la façon dont vous pouvez refactoriser la méthode CreateBankAccounts :*

    **Extrait de code A : Utiliser l’interface **

    ```csharp

    interface IAccountFactory
    {
        BankAccount Create(int index);
    }
    class BankAccountFactory : IAccountFactory
    {
        private readonly RandomDataGenerator _randomDataGenerator;
        public BankAccountFactory(RandomDataGenerator randomDataGenerator)
        {
            _randomDataGenerator = randomDataGenerator;
        }
        public BankAccount Create(int index)
        {
            double initialBalance = _randomDataGenerator.GenerateRandomBalance(10, 50000);
            string accountHolderName = _randomDataGenerator.GenerateRandomAccountHolder();
            string accountType = _randomDataGenerator.GenerateRandomAccountType();
            DateTime dateOpened = _randomDataGenerator.GenerateRandomDateOpened();
            return new BankAccount($"Account {index + 1}", initialBalance, accountHolderName, accountType, dateOpened);
        }
    }
    // In the `Program` class, you would then use the `IAccountFactory` to create accounts:
    interface IAccountFactory
    {
        BankAccount Create(int index);
    }
    class BankAccountFactory : IAccountFactory
    {
        private readonly RandomDataGenerator _randomDataGenerator;
        public BankAccountFactory(RandomDataGenerator randomDataGenerator)
        {
            _randomDataGenerator = randomDataGenerator;
        }
        public BankAccount Create(int index)
        {
            double initialBalance = _randomDataGenerator.GenerateRandomBalance(10, 50000);
            string accountHolderName = _randomDataGenerator.GenerateRandomAccountHolder();
            string accountType = _randomDataGenerator.GenerateRandomAccountType();
            DateTime dateOpened = _randomDataGenerator.GenerateRandomDateOpened();
            return new BankAccount($"Account {index + 1}", initialBalance, accountHolderName, accountType, dateOpened);
        }
    }

    ```

    **Extrait de code B : Duplication **

    ```csharp

    static void SimulateOperations(List<BankAccount> accounts, int numberOfOperations, Action<BankAccount, double> operation)
    {
        foreach (BankAccount account in accounts)
        {
            for (int i = 0; i < numberOfOperations; i++)
            {
                double transactionAmount = GenerateRandomBalance(-500, 500);
                try
                {
                    operation(account, transactionAmount);
                    Console.WriteLine($"Operation: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                }
                catch (Exception ex)
                {
                    Console.WriteLine($"Operation failed: {ex.Message}");
                }
            }
            Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
        }
    }
    // Then you can call this method like this:
    SimulateOperations(accounts, NumberOfTransactions, (account, amount) => {
        if (amount >= 0)
        {
            account.Credit(amount);
        }
        else
        {
            account.Debit(-amount);
        }
    });

    ```

    > [!NOTE]
    > Vous n’avez pas besoin d’implémenter les suggestions de mise à jour générées par GitHub Copilot à partir de votre troisième invite. L’examen des suggestions peut fournir des insights sur la progression du processus d’amélioration du code.

Les deux démonstrations suivantes couvrent les sujets suivants :

- Améliorer la fiabilité et les performances du code à l’aide de GitHub Copilot Chat
- Améliorer la sécurité du code à l’aide de GitHub Copilot Chat

## Résumé

Dans cette version de démonstration, vous avez utilisé GitHub Copilot Chat pour générer des suggestions qui vous aident à améliorer la qualité du code dans un exemple d’application. Vous avez élaboré des messages-guides axés sur l’amélioration de la lisibilité, de la maintenabilité et de la modularité du code. Vous avez examiné les suggestions fournies par GitHub Copilot Chat et implémenté les mises à jour qui ont contribué à améliorer la qualité du code. Vous avez également envisagé des suggestions supplémentaires susceptibles d’améliorer davantage votre code.
