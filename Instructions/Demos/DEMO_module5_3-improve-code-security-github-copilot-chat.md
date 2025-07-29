---
demo:
  title: "Démonstration\_: Améliorer la sécurité du code à l’aide de GitHub Copilot Chat"
  module: 'Module 5: Implement code improvements using GitHub Copilot tools'
---

# Démonstration : Améliorer la sécurité du code à l’aide de GitHub Copilot Chat

## Instructions

Les activités de la version de démonstration sont conçues pour un environnement qui inclut les ressources suivantes :

- Visual Studio Code.
- L’extension du kit de développement C# pour Visual Studio Code.
- Les extensions GitHub Copilot et GitHub Copilot Chat pour Visual Studio Code. Il est nécessaire de disposer d’un compte GitHub avec un abonnement actif pour GitHub Copilot.
- Des exemples de projets de code créés en C#.

**REMARQUE** : Nous recommandons aux instructeurs d’utiliser leur propre compte GitHub et leur abonnement GitHub Copilot pour les démonstrations. Ainsi vous pouvez contrôler et personnaliser votre environnement de développement. Cette démarche facilite également l’ajustement des démonstrations en fonction des besoins de vos salles de classe.

**IMPORTANT** : Si vous choisissez d’exécuter les démonstrations dans l’environnement de laboratoire hébergé plutôt que sur votre ordinateur personnel instructeur, vous pouvez décompresser les exemples d’applications dans l’environnement hébergé. Vous devez configurer les extensions GitHub Copilot dans l’environnement hébergé avant de pouvoir exécuter les démonstrations. Vous pouvez constater que l’environnement hébergé est plus lent que votre environnement local. Vous devrez probablement ajuster l’allure des démonstrations en conséquence.

### Présentez la version de démonstration

La sécurité du code fait référence aux mesures prises pour protéger les logiciels contre les accès non autorisés, les violations de données et d’autres menaces de sécurité. La sécurité du code est un aspect essentiel du développement logiciel qui consiste à protéger les applications et les systèmes contre les menaces de sécurité. Améliorer la sécurité de votre code protège vos applications et systèmes contre les menaces de sécurité.

> [!IMPORTANT]
> Expliquez aux étudiants que cette version de démonstration ne concerne pas les meilleures pratiques de développement de code sécurisé. Il se concentre plutôt sur l’utilisation de GitHub Copilot Chat pour générer des suggestions visant à améliorer la sécurité du code dans un exemple d’application. Les suggestions ne représentent pas les meilleures pratiques ni des solutions complètes pour développer un code sécurisé. Les développeurs doivent faire appel à leur bon sens et à leur expertise pour évaluer et mettre en œuvre les suggestions fournies par GitHub Copilot Chat. L’adoption des recommandations de GitHub Copilot ne remplace en aucun cas les processus de révision et de tests de code approfondis.

#### Sécurité du code

Assurer la sécurité du code est la responsabilité de tous, pas seulement du développeur. Cependant, les développeurs jouent un rôle crucial en veillant à ce que le code qu’ils écrivent suit les pratiques de codage sécurisé. Les pratiques de codage sécurisé s’assurent que les vulnérabilités des logiciels ne soient pas exploitées par des attaquants. En suivant les pratiques de codage sécurisé, les développeurs protègent le logiciel contre les menaces de sécurité et s’assurent qu’il est sécurisé et fiable.

Les sections suivantes fournissent une vue d’ensemble des processus de sécurité du code que vos étudiants doivent connaître.

##### Évaluer la sécurité du code à l’aide d’une approche complète

Lors de l’évaluation de la sécurité du code, il est important d’adopter une approche complète qui englobe divers aspects du cycle de vie du développement du logiciel. Voici quelques considérations clés à prendre en compte :

- Pratiques de codage sécurisé : le respect des normes et des directives de codage sécurisé pour prévenir les vulnérabilités.
- Outils d’analyse du code : l’utilisation d’outils d’analyse du code statique et dynamique pour détecter les failles de sécurité.
- Gestion des dépendances : la vérification que les bibliothèques et dépendances tierces sont à jour et exemptes de vulnérabilités connues.
- Authentification et autorisation : l’implémentation de mécanismes d’authentification et d’autorisation robustes pour se protéger contre les accès non autorisés.
- Protection des données : le chiffrement des données sensibles, à la fois au repos et en transit pour prévenir les violations de données.
- Gestion des erreurs : le développement de procédures sécurisées de gestion des erreurs qui ne divulguent pas d’informations sensibles.
- Tests de sécurité : l’exécution de tests de sécurité approfondis, notamment des tests d’intrusion et des évaluations de vulnérabilité.
- Conformité : la vérification de la conformité du code aux normes et aux réglementations de sécurité pertinentes.
- Apprentissage et formation : la mise à disposition aux développeurs d’un apprentissage et d’une formation continus en matière de sécurité pour les tenir informés des dernières menaces et des meilleures pratiques.
- Réponse aux incidents : la préparation d’un plan de réponse aux incidents bien défini. En cas de violation de la sécurité, le plan de réponse aux incidents doit être accessible.

L’examen de ces facteurs et l’intégration des meilleures pratiques de sécurité dans votre processus de développement contribuent à la création de contenus et d’applications sécurisés.

##### Effectuer des révisions de sécurité du code

Lorsque vous travaillez à garantir la sécurité du code, les développeurs doivent passer en revue les aspects suivants de leur code :

- Exactitude : la vérification que le code soit exempt d’erreurs logiques et de défauts susceptibles d’entraîner des vulnérabilités de sécurité.
- Sécurité : l’évaluation du code pour garantir qu’il respecte les meilleures pratiques de sécurité et ne présente pas de vulnérabilités.
- Diagnostics : l’inclusion de fonctionnalités appropriées de journalisation et de diagnostic pour détecter et répondre aux incidents de sécurité.
- Erreurs de conception ou limitations : la révision de la conception du code pour vous assurer qu’il n’y a pas de défauts ou de limitations pouvant être exploités.
- Scalabilité et performances : la considération du niveau de performance et de la scalabilité du code. Des niveaux de performance et une scalabilité médiocres peuvent affecter la sécurité dans des scénarios à charge élevée.
- Localisation : la garantie que le code gère de manière sécurisée les différentes paramètres régionaux, ce qui peut affecter la mise en forme et la représentation des données.
- Accessibilité (expérience utilisateur) : la vérification que les mesures de sécurité n’affectent pas négativement l’accessibilité et l’expérience utilisateur.
- Test : la révision des stratégies de test et l’assurance que les tests de sécurité sont approfondis et couvrent tous les aspects du code.
- Instrumentation : la mise en place du code doit être effectuée de manière à prendre en charge l’analyse de la sécurité et la détection des menaces.
- Cohérence et conventions de style de code : le maintien d’un style de codage cohérent qui suit les directives et les normes de codage sécurisé.

Lorsque les développeurs passent en revue ces aspects, ils peuvent améliorer considérablement la sécurité de leur code. Les révisions de code aident les développeurs à contribuer à l’état global de la sécurité des logiciels qu’ils développent.

##### Analyser les vulnérabilités du code

Certaines parties d’une application sont plus vulnérables aux attaques de sécurité et il est essentiel de se concentrer sur la sécurisation de ces zones. Voici quelques-unes des zones les plus vulnérables :

- Points d’intégration : les révisions de la conception de sécurité doivent être effectuées pour les points d’intégration avec les équipes des produits dépendants. Les révisions sont essentielles pour les produits traitant des données à fort impact sur l’activité (HBI, High Business Impact) ou des applications et services d’entreprise.
- Systèmes internes : les incidents internes constituent une cause courante de violations de la sécurité, en particulier dans les petites entreprises.
- Systèmes de messagerie : les serveurs de messagerie, en particulier ceux qui ne sont pas pris en charge ou non corrigés, sont toujours vulnérables.
- Bases de données et stockage : le pré-chiffrage des données sensibles attendu par les bases de données avant le stockage peut les rendre vulnérables si les données ne sont pas chiffrées comme prévu.
- L’environnement d’exécution : la détection des attaques sur une application en temps réel, rendue possible par des technologies telles que la Protection automatique des applications en exécution (RASP, Runtime Application Self-Protection), fait de l’environnement d’exécution une zone critique à sécuriser.
- Applications web : les applications web sont souvent la cible d’attaquants utilisant des méthodes telles que l’injection de code SQL, le scripting inter-site (XSS, Cross site scripting) et les dépassements de mémoire tampon.
- Points de terminaison : les appareils et les applications sont exposés à des cyber-attaques. Il est essentiel de réduire la surface d’attaque en utilisant des fonctionnalités telles que l’atténuation des ransomware, le contrôle des applications, la protection web et le pare-feu réseau.

Les développeurs et les équipes de sécurité doivent hiérarchiser ces domaines et implémenter des mesures de sécurité fortes pour se protéger contre les attaques potentielles. Les révisions de sécurité, les mises à jour et l’adhésion aux meilleures pratiques, toutes effectuées régulièrement, atténuent ces vulnérabilités.

##### Rechercher des failles de sécurité courantes

Les développeurs peuvent rencontrer diverses failles de sécurité dans leur code, ce qui peut entraîner des vulnérabilités si elles ne sont pas correctement traitées. Voici quelques failles de sécurité typiques :

- Failles d’injection : telles que les injections SQL, NoSQL, OS et LDAP, où des données non approuvées sont envoyées à un interpréteur dans le cadre d’une commande ou d’une requête.
- Authentification compromise : lorsque l’authentification et la gestion des sessions sont implémentées de manière incorrecte, l’authentification peut être compromise. De bonnes implémentations garantissent que les mots de passe, les clés et les jetons de session ne sont pas compromis par des attaquants.
- Exposition de données sensibles : une protection inadéquate des données sensibles peut entraîner une exposition lors du transfert sur le réseau ou au repos.
- Contrôle d’accès défaillant : les restrictions qui contrôlent l’accès accordé aux utilisateurs authentifiés ne sont pas correctement appliquées.
- Scripting inter-site (XSS) : les failles XSS se produisent chaque fois qu’une application inclut des données non approuvées dans une page web sans validation ou échappement appropriés.
- Désérialisation non sécurisée : cela peut entraîner une exécution de code à distance, des attaques par rejeu, des attaques par injection et des attaques par élévation des privilèges.
- Journalisation et analyse insuffisantes : la journalisation et l’analyse insuffisantes, associées à une intégration manquante ou inefficace à la réponse aux incidents, permettent la poursuite des attaques.
- Références directes non sécurisées à des objets (IDOR, Insecure Direct Object References) : un type de problème de contrôle d’accès qui survient lorsqu’une application fournit un accès direct à des objets en fonction de l’entrée fournie par l’utilisateur.
- Contrôle d’accès manquant au niveau de la fonction : parfois, une application ne protège pas correctement les contrôles d’accès au niveau de la fonction, permettant ainsi aux attaquants de falsifier des requêtes d’accès aux fonctionnalités sans autorisation appropriée.

De nombreuses autres failles de sécurité peuvent être trouvées dans le code. Il est important que les développeurs utilisent des outils et les meilleures pratiques pour identifier et résoudre ces problèmes de manière proactive.

### Développer des prompts pour GitHub Copilot Chat

Les prompts que vous écrivez pour GitHub Copilot Chat doivent fournir un contexte et une intention clairement définis. Tenez compte des suggestions suivantes lors du développement de vos prompts :

- Définissez un contexte externe délimité à un niveau supérieur au code que vous souhaitez mettre à jour. Par exemple, si vous souhaitez améliorer une méthode, spécifiez la classe ou le fichier qui inclut la méthode comme contexte externe. Repérez la méthode comme contexte interne.
- Utilisez les participants de conversation et les variables de conversation pour vous aider à spécifier le contexte. Vous pouvez utiliser les variables de conversation `#file:` et `#selection` pour identifier le code spécifique sur lequel vous vous concentrez. Vous pouvez également inclure l’espace de travail complet (`@workspace`) le cas échéant. Reportez-vous à la sélection du fichier ou du code dans la partie en langage naturel de votre prompt.
- L’intention doit être claire, concise et spécifique. Votre prompt doit spécifier le type d’amélioration que vous souhaitez atteindre.

Pendant cette phase, vous passez en revue le projet **APL2007M5BankAccount-Security**, puis vous créez trois requêtes pour GitHub Copilot Chat. Les prompts se concentrent sur l’amélioration de la sécurité du code.

Suivez les étapes ci-dessous pour effectuer cette phase de la version de démonstration :

1. Ouvrez le projet **APL2007M5BankAccount-Security**, puis passez en revue les fichiers de code **Program.cs** et **BankAccount.cs**.

    Le fichier **Program.cs** contient le code d’une application bancaire simple qui simule la création de comptes bancaires, de transactions et de transferts.

    Le fichier **BankAccount.cs** contient le code de la classe `BankAccount`, qui représente un compte bancaire avec des fonctionnalités de base, telles que le dépôt, le retrait et la consultation du solde.

1. Prenez une minute pour décrire certaines requêtes qui pourraient être utilisées pour améliorer la sécurité du code.

    Pour ce projet, vous pouvez utiliser les prompts suivants pour générer des suggestions visant à améliorer la sécurité de votre code :

    Requête : `@workspace /explain How can I implement authentication in the [selected code]?` (attacher BankAccount.cs au contexte Conversation)

    Requête : `@workspace /explain How can I protect sensitive data in the [selected code]?` (attacher BankAccount.cs au contexte Conversation)

    Requête : `@workspace /explain How can I implement logging of suspicious account activities of the [selected code]?` (attacher BankAccount.cs au contexte Conversation)

    Requête : `@workspace /explain How can I improve the security of exception handling in the [selected code]?` (attacher BankAccount.cs au contexte Conversation)

    Requête : `@workspace /explain How can I improve the security of the [selected code]?` (attacher BankAccount.cs au contexte Conversation)

    Requête : `@workspace /explain How can I improve the security of the [selected code]?` (attacher Program.cs au contexte Conversation)

1. Sélectionnez trois requêtes à utiliser pendant le reste de la version de démonstration.

    Essayez de sélectionner deux prompts qui traitent des problèmes de sécurité dans le fichier BankAccount.cs et un dans le fichier Program.cs. Dans cette version de démonstration, la classe BankAccount représente votre « produit ». Le fichier Program.cs utilise la classe BankAccount pour simuler des activités et des transactions de compte.

### Améliorer la sécurité du code de la classe BankAccount à l’aide de GitHub Copilot Chat

Développer un code sécurisé est essentiel pour tout projet de logiciel. Le niveau de sécurité requis dépend de la nature de l’application et des données qu’elle traite.

Dans cette version de démonstration, vous utilisez GitHub Copilot Chat pour générer des suggestions pour améliorer la sécurité de la classe BankAccount dans le projet **APL2007M5BankAccount-Security**.

GitHub Copilot Chat peut être utilisé pour améliorer la sécurité du code. Vos prompts peuvent diriger GitHub Copilot à générer des suggestions pour améliorer l’authentification, la protection des données, la journalisation et des dizaines d’autres sujets. Vous pouvez également créer des prompts de grande ampleur qui sollicitent des suggestions globales pour améliorer la sécurité du code. L’utilisation d’une combinaison de prompts spécifiques et généraux peut vous aider à cibler les domaines nécessitant des améliorations et à mettre en œuvre les modifications nécessaires.

> [!TIP]
> L’implémentation et le test des mises à jour suggérées prennent un certain temps. Ce facteur doit être pris en compte dans le cadre de cette version de démonstration. La sélection de prompts axés sur des domaines spécifiques d’amélioration peut vous aider à gérer votre temps. Les prompts dont l’ampleur est trop grande peuvent engendrer de nombreuses suggestions, voire des propositions complexes, rendant leur évaluation et leur mise en œuvre ardues dans des délais restreints. Une fois créés, vos prompts peuvent être mis à jour avec des détails plus spécifiques si vous remarquez que les mises à jour suggérées sont trop vastes ou trop complexes.

1. Vérifiez que le projet génère et s’exécute sans erreur.

    Les avertissements sont tolérables tant que l’application s’exécute, mais les erreurs doivent être résolues avant de commencer à utiliser GitHub Copilot Chat.

1. Ouvrez le fichier BankAccount.cs dans Visual Studio Code, puis sélectionnez tout le code dans le fichier.

1. Ouvrez la vue Conversation.

1. Dans la vue Conversation, utilisez le bouton **Attacher le contexte** pour ajouter des fichiers pertinents au contexte Conversation, puis entrez votre requête.

1. Examinez les suggestions fournies par GitHub Copilot Chat.

    Par exemple, supposons que vous effectuiez les actions suivantes :

    - Vous ouvrez le fichier BankAccount.cs et vous sélectionnez tout le code.
    - Vous choisissez l’invite suivante : `@workspace /explain How can I implement authentication in the BankAccount.cs file?`
    - Vous ouvrez la vue Conversation et vous attachez les fichiers BankAccount.cs et Program.cs au contexte Conversation.
    - Vous entrez l’invite dans la vue Conversation.

    GitHub Copilot Chat suggère des mises à jour qui sont similaires à la réponse suivante :

    *L’implémentation de l’authentification dans ce contexte impliquerait généralement l’ajout d’une méthode à la classe BankAccount qui vérifie l’identité du titulaire du compte avant d’autoriser certaines opérations. Cette opération peut être effectuée à l’aide d’un mot de passe, d’un code PIN ou d’une autre forme d’authentification.*

    *Voici un exemple simple de la façon dont vous pouvez ajouter l’authentification par mot de passe à la classe BankAccount :*

    ```csharp

    public class BankAccount
    {
        // Existing code...
        private string password;
        public BankAccount(string accountNumber, double initialBalance, string accountHolderName, string accountType, DateTime dateOpened, string password)
        {
            // Existing code...
    
            this.password = password;
        }
        public bool Authenticate(string password)
        {
            return this.password == password;
        }
        public void Credit(double amount, string password)
        {
            if (!Authenticate(password))
            {
                throw new Exception("Authentication failed.");
            }
            // Existing code...
        }
        // Similar changes would be made to the Debit, Transfer, and other methods...
    }

    ```

    *Dans cet exemple, un mot de passe est ajouté en tant que paramètre au constructeur de BankAccount et stocké dans un champ privé. Une méthode d’authentification est ajoutée pour vérifier si le mot de passe fourni correspond au mot de passe stocké. La méthode Credit (et d’autres méthodes qui devraient exiger l’authentification) est modifiée pour prendre un mot de passe en tant qu’argument et appeler Authenticate avant d’effectuer l’opération.*

    *Il s’agit d’une forme d’authentification très simple qui n’est pas suffisamment sécurisée pour des applications réelles. Dans une application réelle, vous voudriez hacher et saler le mot de passe avant de le stocker, et vous auriez besoin d’utiliser des méthodes sécurisées pour transmettre le mot de passe de l’utilisateur à l’application. Vous pourriez également envisager d’utiliser l’authentification à 2 facteurs ou d’autres méthodes plus sécurisées.*

1. Implémentez les mises à jour suggérées qui aident à améliorer la sécurité du code pour votre classe `BankAccount`.

    Le fichier Program.cs doit être mis à jour pour utiliser le mot de passe et l’authentification ajoutés à la classe BankAccount. Vous pouvez utiliser GitHub Copilot Chat pour générer des suggestions de mise à jour du fichier Program.cs.

    1. Sélectionnez le contenu du fichier Program.cs, attachez les fichiers Program.cs et BankAccount.cs au contexte Conversation, puis entrez la requête suivante dans la vue Conversation :

        ```plaintext
        @workspace /Explain How can I update the Program.cs file to use the password and authentication added to BankAccount.cs?
        ```

    1. Passez en revue les suggestions fournies par GitHub Copilot Chat, puis implémentez les mises à jour suggérées.

    1. Pour vous assurer qu’aucune erreur n’a été introduite par les modifications, compilez et exécutez votre solution avant de continuer.

        Utilisez GitHub Copilot pour résoudre les problèmes identifiés lors du processus de build.

    > [!IMPORTANT]
    > Assurez-vous que vos étudiants comprennent que cette forme d’authentification très simple n’est pas suffisamment sécurisée pour des applications réelles. Dans une application réelle, vous voudriez hacher et saler le mot de passe avant de le stocker, et vous auriez besoin d’utiliser des méthodes sécurisées pour transmettre le mot de passe de l’utilisateur à l’application. Vous pourriez également envisager d’utiliser l’authentification à deux facteurs ou d’autres méthodes plus sécurisées.

1. Vérifiez que votre application est générée et qu’elle s’exécute avant de continuer.

1. Sélectionnez tout le code dans le fichier BankAccount.cs, puis entrez votre deuxième prompt dans la vue Conversation.

1. Vérifiez les suggestions fournies par GitHub Copilot Chat.

    Par exemple, supposons que vous effectuiez les actions suivantes :

    - Vous ouvrez le fichier BankAccount.cs et vous sélectionnez tout le code.
    - Vous choisissez l’invite suivante : `@workspace /explain How can I protect account numbers and account holder names in the selected code?`
    - Vous ouvrez la vue Conversation et vous attachez les fichiers BankAccount.cs et Program.cs au contexte Conversation.
    - Vous entrez l’invite dans la vue Conversation.

    GitHub Copilot Chat suggère des mises à jour qui sont similaires à la réponse suivante :

    *Pour protéger les données sensibles telles que les numéros de compte et les noms des titulaires de compte dans votre classe BankAccount, vous pouvez effectuer les étapes suivantes :*

    *1. Utilisez l’encapsulation :*

    *- Rendez privées les propriétés sensibles et fournissez un accès contrôlé via des méthodes.*

    *2. Chiffrez les données sensibles :*

    *- Utilisez le chiffrement pour stocker les données sensibles de façon sécurisée.*

    *3. Évitez le stockage en texte clair :*

    * : Vérifiez que les données sensibles ne sont pas stockées ou transmises en texte clair.*

    *Implémentation mise à jour*

    *Voici une version de BankAccount.cs mise à jour qui utilise le chiffrement pour les numéros de compte et les noms des titulaires de compte :*

    ```csharp

    using System;
    using System.Security.Cryptography;
    using System.Text;
    namespace BankAccountApp
    {
        public class InsufficientFundsException : Exception
        {
            public double AttemptedAmount { get; }
            public double CurrentBalance { get; }
    
            public InsufficientFundsException(double attemptedAmount, double currentBalance)
                : base($"Insufficient balance for debit. Attempted to debit {attemptedAmount}, but current balance is {currentBalance}.")
            {
                AttemptedAmount = attemptedAmount;
                CurrentBalance = currentBalance;
            }
        }
        public class InvalidAccountTypeException : Exception
        {
            public string AccountType { get; }
            public InvalidAccountTypeException(string accountType)
                : base($"Invalid account type: {accountType}.")
            {
                AccountType = accountType;
            }
        }
        public class InvalidAccountNumberException : Exception
        {
            public string AccountNumber { get; }
            public InvalidAccountNumberException(string accountNumber)
                : base($"Invalid account number: {accountNumber}.")
            {
                AccountNumber = accountNumber;
            }
        }
        public class InvalidAccountHolderNameException : Exception
        {
            public string AccountHolderName { get; }
            public InvalidAccountHolderNameException(string accountHolderName)
                : base($"Invalid account holder name: {accountHolderName}.")
            {
                AccountHolderName = accountHolderName;
            }
        }
        public class InvalidDateOpenedException : Exception
        {
            public DateTime DateOpened { get; }
            public InvalidDateOpenedException(DateTime dateOpened)
                : base($"Invalid date opened: {dateOpened}.")
            {
                DateOpened = dateOpened;
            }
        }
        public class InvalidInitialBalanceException : Exception
        {
            public double InitialBalance { get; }
            public InvalidInitialBalanceException(double initialBalance)
                : base($"Invalid initial balance: {initialBalance}.")
            {
                InitialBalance = initialBalance;
            }
        }
        public class InvalidInterestRateException : Exception
        {
            public double InterestRate { get; }
            public InvalidInterestRateException(double interestRate)
                : base($"Invalid interest rate: {interestRate}.")
            {
                InterestRate = interestRate;
            }
        }
        public class InvalidTransferAmountException : Exception
        {
            public double TransferAmount { get; }
            public InvalidTransferAmountException(double transferAmount)
                : base($"Invalid transfer amount: {transferAmount}.")
            {
                TransferAmount = transferAmount;
            }
        }
        public class InvalidCreditAmountException : Exception
        {
            public double CreditAmount { get; }
            public InvalidCreditAmountException(double creditAmount)
                : base($"Invalid credit amount: {creditAmount}.")
            {
                CreditAmount = creditAmount;
            }
        }
        public class InvalidDebitAmountException : Exception
        {
            public double DebitAmount { get; }
            public InvalidDebitAmountException(double debitAmount)
                : base($"Invalid debit amount: {debitAmount}.")
            {
                DebitAmount = debitAmount;
            }
        }
        public class AuthenticationException : Exception
        {
            public AuthenticationException(string message) : base(message) { }
        }
        public class BankAccount
        {
            public enum AccountTypes
            {
                Savings,
                Checking,
                MoneyMarket,
                CertificateOfDeposit,
                Retirement
            }
            private string EncryptedAccountNumber { get; }
            private string EncryptedAccountHolderName { get; }
            public double Balance { get; private set; }
            public AccountTypes AccountType { get; }
            public DateTime DateOpened { get; }
            private const double MaxTransferAmountForDifferentOwners = 500;
            private string Username { get; }
            private string Password { get; }
            public BankAccount(string accountNumber, double initialBalance, string accountHolderName, string accountType, DateTime dateOpened, string username, string password)
            {
                if (accountNumber.Length != 10)
                {
                    throw new InvalidAccountNumberException(accountNumber);
                }
                if (initialBalance < 0)
                {
                    throw new InvalidInitialBalanceException(initialBalance);
                }
                if (accountHolderName.Length < 2)
                {
                    throw new InvalidAccountHolderNameException(accountHolderName);
                }
                if (dateOpened > DateTime.Now)
                {
                    throw new InvalidDateOpenedException(dateOpened);
                }
                EncryptedAccountNumber = Encrypt(accountNumber);
                EncryptedAccountHolderName = Encrypt(accountHolderName);
                Balance = initialBalance;
                AccountType = (AccountTypes)Enum.Parse(typeof(AccountTypes), accountType);
                DateOpened = dateOpened;
                Username = username;
                Password = password;
            }
            public void Credit(double amount)
            {
                if (amount < 0)
                {
                    throw new InvalidCreditAmountException(amount);
                }
                Balance += amount;
            }
            public void Debit(double amount)
            {
                if (amount < 0)
                {
                    throw new InvalidDebitAmountException(amount);
                }
                if (Balance >= amount)
                {
                    Balance -= amount;
                }
                else
                {
                    throw new InsufficientFundsException(amount, Balance);
                }
            }
            public double GetBalance()
            {
                return Balance;
            }
            public void Transfer(BankAccount toAccount, double amount)
            {
                ValidateTransferAmount(amount);
                ValidateTransferLimitForDifferentOwners(toAccount, amount);
                if (Balance >= amount)
                {
                    Debit(amount);
                    toAccount.Credit(amount);
                }
                else
                {
                    throw new InsufficientFundsException(amount, Balance);
                }
            }
            private void ValidateTransferAmount(double amount)
            {
                if (amount < 0)
                {
                    throw new InvalidTransferAmountException(amount);
                }
            }
            private void ValidateTransferLimitForDifferentOwners(BankAccount toAccount, double amount)
            {
                if (Decrypt(EncryptedAccountHolderName) != Decrypt(toAccount.EncryptedAccountHolderName) && amount > MaxTransferAmountForDifferentOwners)
                {
                    throw new Exception("Transfer amount exceeds maximum limit for different account owners.");
                }
            }
            public void PrintStatement()
            {
                Console.WriteLine($"Account Number: {Decrypt(EncryptedAccountNumber)}, Balance: {Balance}");
            }
            public double CalculateInterest(double interestRate)
            {
                if (interestRate < 0)
                {
                    throw new InvalidInterestRateException(interestRate);
                }
                return Balance * interestRate;
            }
            public void Authenticate(string username, string password)
            {
                if (Username != username || Password != password)
                {
                    throw new AuthenticationException("Invalid username or password.");
                }
            }
            private string Encrypt(string plainText)
            {
                using (Aes aes = Aes.Create())
                {
                    aes.Key = Encoding.UTF8.GetBytes("A very strong key"); // Use a secure key
                    aes.IV = Encoding.UTF8.GetBytes("A strong IV123456"); // Use a secure IV
                    ICryptoTransform encryptor = aes.CreateEncryptor(aes.Key, aes.IV);
                    using (var ms = new System.IO.MemoryStream())
                    {
                        using (var cs = new CryptoStream(ms, encryptor, CryptoStreamMode.Write))
                        {
                            using (var sw = new System.IO.StreamWriter(cs))
                            {
                                sw.Write(plainText);
                            }
                        }
                        return Convert.ToBase64String(ms.ToArray());
                    }
                }
            }
            private string Decrypt(string cipherText)
            {
                using (Aes aes = Aes.Create())
                {
                    aes.Key = Encoding.UTF8.GetBytes("A very strong key"); // Use a secure key
                    aes.IV = Encoding.UTF8.GetBytes("A strong IV123456"); // Use a secure IV
                    ICryptoTransform decryptor = aes.CreateDecryptor(aes.Key, aes.IV);
                    using (var ms = new System.IO.MemoryStream(Convert.FromBase64String(cipherText)))
                    {
                        using (var cs = new CryptoStream(ms, decryptor, CryptoStreamMode.Read))
                        {
                            using (var sr = new System.IO.StreamReader(cs))
                            {
                                return sr.ReadToEnd();
                            }
                        }
                    }
                }
            }
        }
    }

    ```

    *Utilisation :*

    *– Vérifiez que vous disposez des bibliothèques de chiffrement nécessaires. L’exemple ci-dessus utilise le chiffrement AES avec une clé et un vecteur d’initialisation codés en dur, à des fins de simplicité. Dans une application réelle, vous devez gérer les clés et les vecteurs d’initialisation de façon sécurisée, en utilisant éventuellement un service de gestion de clés.*

    > [!IMPORTANT]
    > Dans une application réelle, vous devez gérer les clés et les vecteurs d’initialisation de façon sécurisée, en utilisant éventuellement un service de gestion des clés. Les exemples fournis dans cette formation identifient des aspects à améliorer, mais ne représentent pas les meilleures pratiques pour le chiffrement sécurisé. Vous pouvez utiliser GitHub Copilot Chat pour rechercher des suggestions supplémentaires afin d’améliorer le chiffrement et la protection des données dans votre application.

1. Pas besoin d’implémenter les mises à jour suggérées pour la deuxième requête.

    Dans cet exemple, les mises à jour suggérées permettraient d’améliorer la sécurité de l’application, mais nécessitent une configuration approfondie ainsi que des mises à jour importantes du fichier Program.cs, ce qui dépasse la portée de cette version de démonstration.

### Améliorer la sécurité du code de la classe Program à l’aide de GitHub Copilot Chat

1. Ouvrez le fichier Program.cs dans Visual Studio Code, puis sélectionnez tout le code dans le fichier.

1. Ouvrez la vue Conversation, puis entrez le premier prompt que vous avez préparé pour la classe Program.

1. Vérifiez les suggestions fournies par GitHub Copilot Chat.

    Par exemple, supposons que vous effectuiez les actions suivantes :

    - Vous ouvrez le fichier Program.cs et vous sélectionnez tout le code.
    - Vous choisissez l’invite suivante : `@workspace /explain How can I improve the security of the Program.cs file?`
    - Vous ouvrez la vue Conversation et vous attachez les fichiers BankAccount.cs et Program.cs au contexte Conversation.
    - Vous entrez l’invite dans la vue Conversation.

    GitHub Copilot Chat suggère des mises à jour qui sont similaires à la réponse suivante :

    *Pour améliorer la sécurité du fichier Program.cs, vous devez vous concentrer sur les aspects suivants :*

    *1. Sécurisez la gestion des mots de passe :*

    *– Utilisez le hachage de mot de passe sécurisé et évitez de stocker les mots de passe dans un texte en clair.*
    *– Utilisez une bibliothèque telle que BCrypt.Net pour le hachage des mots de passe.*

    *2. Chiffrez les données sensibles :*

    *- Chiffrez les données sensibles telles que les numéros de compte et les noms des titulaires de compte.*

    *3. Évitez les mots de passe codés en dur :*

    *– Évitez d’utiliser des mots de passe codés en dur. Privilégiez la génération de mots de passe aléatoires robustes ou invitez les utilisateurs à créer les leurs.*

    *4. Utilisez la génération de nombres aléatoires sécurisés :*

    *- Utilisez un générateur de nombres aléatoires sécurisés par chiffrement pour générer des données sensibles.*

    *Implémentation mise à jour*

    *Voici une version mise à jour de Program.cs qui intègre ces améliorations :*

    ```csharp

    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Security.Cryptography;
    using System.Text;
    using System.Threading.Tasks;
    namespace BankAccountApp
    {
        class Program
        {
            private static readonly Random random = new Random();
            private const int MaxYearsBack = 10;
            private const int NumberOfAccounts = 20;
            private const int NumberOfTransactions = 100;
            private const double minTransactionAmount = -500.0;
            private const double maxTransactionAmount = 500.0;
            private const double minAccountStart = 200.0;
            private const double maxAccountStart = 1000.0;
            static async Task Main()
            {
                List<BankAccount> accounts = CreateBankAccounts(NumberOfAccounts);
                await SimulateTransactionsAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
                await SimulateTransfersAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
            }
            static List<BankAccount> CreateBankAccounts(int numberOfAccounts)
            {
                List<BankAccount> accounts = new();
                int createdAccounts = 0;
                while (createdAccounts < numberOfAccounts)
                {
                    try
                    {
                        double initialBalance = GenerateRandomDollarAmount(true, minAccountStart, maxAccountStart);
                        string accountHolderName = GenerateRandomAccountHolder();
                        string accountType = GenerateRandomAccountType();
                        DateTime dateOpened = GenerateRandomDateOpened();
                        string accountNumber = "102000" + random.Next(1000, 9999).ToString();
                        string username = "user" + createdAccounts;
                        string password = GenerateSecurePassword();
                        BankAccount account = new(accountNumber, initialBalance, accountHolderName, accountType, dateOpened, username, password);
                        accounts.Add(account);
                        createdAccounts++;
                    }
                    catch (ArgumentException ex)
                    {
                        Console.WriteLine($"Account creation failed due to invalid argument: {ex.Message}");
                        // Log the exception
                    }
                    catch (Exception ex)
                    {
                        Console.WriteLine($"Account creation failed: {ex.Message}");
                        // Log the exception
                    }
                    finally
                    {
                        // Any cleanup code would go here.
                    }
                }
                return accounts;
            }
            static async Task SimulateTransactionsAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                var tasks = accounts.Select(async account =>
                {
                    for (int i = 0; i < numberOfTransactions; i++)
                    {
                        double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                        try
                        {
                            account.Authenticate(account.Username, account.Password); // Authenticate before transaction
                            if (transactionAmount >= 0)
                            {
                                account.Credit(transactionAmount);
                                Console.WriteLine($"Credit: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                            }
                            else
                            {
                                account.Debit(-transactionAmount);
                                Console.WriteLine($"Debit: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                            }
                        }
                        catch (Exception ex)
                        {
                            Console.WriteLine($"Transaction failed: {ex.Message}");
                        }
                    }
                    Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                });
                await Task.WhenAll(tasks);
            }
            static async Task SimulateTransfersAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                var tasks = accounts.Select(async account =>
                {
                    for (int i = 0; i < numberOfTransactions; i++)
                    {
                        double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                        try
                        {
                            account.Authenticate(account.Username, account.Password); // Authenticate before transfer
                            BankAccount toAccount = accounts[random.Next(accounts.Count)];
                            toAccount.Authenticate(toAccount.Username, toAccount.Password); // Authenticate target account
                            account.Transfer(toAccount, transactionAmount);
                            Console.WriteLine($"Transfer: {transactionAmount}, From: {account.AccountNumber}, To: {toAccount.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                        }
                        catch (Exception ex)
                        {
                            Console.WriteLine($"Transfer failed: {ex.Message}");
                        }
                    }
                    Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                });
                await Task.WhenAll(tasks);
            }
            static double GenerateRandomDollarAmount(bool isAccount, double min, double max)
            {
                if (isAccount)
                {
                    double accountStartingValue = random.NextDouble() * (max - min) + min;
                    return Math.Round(accountStartingValue, 2);
                }
                else
                {
                    double transactionAmount = random.NextDouble() * random.Next((int)min, (int)max) + random.NextDouble();
                    return Math.Round(transactionAmount, 2);
                }
            }
            static string GenerateRandomAccountHolder()
            {
                string[] accountHolderNames = { "John Smith", "Maria Garcia", "Mohammed Khan", "Sophie Dubois", "Liam Johnson", "Emma Martinez", "Noah Lee", "Olivia Kim", "William Chen", "Ava Wang", "James Brown", "Isabella Nguyen", "Benjamin Wilson", "Mia Li", "Lucas Anderson", "Charlotte Liu", "Alexander Taylor", "Amelia Patel", "Daniel Garcia", "Sophia Kim" };
                var accountHolderName = accountHolderNames[random.Next(0, accountHolderNames.Length)];
                return accountHolderName;
            }
            static string GenerateRandomAccountType()
            {
                string[] accountTypes = { "Savings", "Checking", "Money Market", "Certificate of Deposit", "Retirement" };
                return accountTypes[random.Next(0, accountTypes.Length)];
            }
            static DateTime GenerateRandomDateOpened()
            {
                DateTime startDate = new(DateTime.Today.Year - MaxYearsBack, 1, 1);
                int daysRange = (DateTime.Today - startDate).Days;
                DateTime randomDate = startDate.AddDays(random.Next(daysRange));
                if (randomDate.Year == DateTime.Today.Year && randomDate >= DateTime.Today)
                {
                    randomDate = randomDate.AddDays(-1);
                }
                return randomDate;
            }
            static string GenerateSecurePassword()
            {
                const int passwordLength = 12;
                const string validChars = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ1234567890!@#$%^&*()";
                StringBuilder password = new StringBuilder();
                using (RNGCryptoServiceProvider rng = new RNGCryptoServiceProvider())
                {
                    byte[] uintBuffer = new byte[sizeof(uint)];
                    while (passwordLength > password.Length)
                    {
                        rng.GetBytes(uintBuffer);
                        uint num = BitConverter.ToUInt32(uintBuffer, 0);
                        password.Append(validChars[(int)(num % (uint)validChars.Length)]);
                    }
                }
                return password.ToString();
            }
        }
    }

    ```

1. Notez que les mises à jour de Program.cs ont été centrées sur la génération de nombres aléatoires sécurisés.

    Les autres suggestions s’appliquent à la classe BankAccount et leur implémentation est au-delà du cadre de cette formation.

1. Construisez une requête supplémentaire pour Program.cs qui vise à sécuriser la gestion des exceptions.

1. Vérifiez les suggestions fournies par GitHub Copilot Chat.

    Par exemple, si vous entrez `@workspace /explain How can I implement secure exception handling in the Program.cs file?` dans la vue Conversation, GitHub Copilot Chat suggère des mises à jour similaires à la réponse suivante :

    *Pour implémenter une gestion sécurisée des exceptions dans le fichier Program.cs, vous devez suivre ces meilleures pratiques :*

    *1. Interceptez des exceptions spécifiques :*

    *– Interceptez des exceptions spécifiques plutôt qu’un bloc générique catch (Exception ex). Cette approche permet de comprendre et de gérer les différents types d’erreurs de manière appropriée.*

    *2. Journalisez les exceptions de façon sécurisée :*

    *– Journalisez les exceptions en toute sécurité sans exposer d’informations sensibles. Utilisez un framework de journalisation pour gérer les journaux.*

    *3. Fournissez des messages conviviaux :*

    *- Fournissez des messages d’erreur conviviaux sans révéler de détails internes.*

    *4. Utiliser des blocs finally pour le nettoyage :*

    *- Utilisez des blocs finally pour vous assurer que tout le nettoyage nécessaire est effectué, qu’une exception ait ou non été levée.*

    *5. Évitez d’intercepter des exceptions non critiques :*

    *- Évitez d’intercepter les exceptions qui doivent être autorisées à se propager, comme OutOfMemoryException ou StackOverflowException.*

    *Voici une version mise à jour de Program.cs avec une gestion sécurisée des exceptions :*

    ```csharp

    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Security.Cryptography;
    using System.Text;
    using System.Threading.Tasks;
    namespace BankAccountApp
    {
        class Program
        {
            private static readonly Random random = new Random();
            private const int MaxYearsBack = 10;
            private const int NumberOfAccounts = 20;
            private const int NumberOfTransactions = 100;
            private const double minTransactionAmount = -500.0;
            private const double maxTransactionAmount = 500.0;
            private const double minAccountStart = 200.0;
            private const double maxAccountStart = 1000.0;
            static async Task Main()
            {
                List<BankAccount> accounts = CreateBankAccounts(NumberOfAccounts);
                await SimulateTransactionsAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
                await SimulateTransfersAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
            }
            static List<BankAccount> CreateBankAccounts(int numberOfAccounts)
            {
                List<BankAccount> accounts = new();
                int createdAccounts = 0;
                while (createdAccounts < numberOfAccounts)
                {
                    try
                    {
                        double initialBalance = GenerateRandomDollarAmount(true, minAccountStart, maxAccountStart);
                        string accountHolderName = GenerateRandomAccountHolder();
                        string accountType = GenerateRandomAccountType();
                        DateTime dateOpened = GenerateRandomDateOpened();
                        string accountNumber = "102000" + random.Next(1000, 9999).ToString();
                        string username = "user" + createdAccounts;
                        string password = GenerateSecurePassword();
                        BankAccount account = new(accountNumber, initialBalance, accountHolderName, accountType, dateOpened, username, password);
                        accounts.Add(account);
                        createdAccounts++;
                    }
                    catch (ArgumentException ex)
                    {
                        Console.WriteLine($"Account creation failed due to invalid argument: {ex.Message}");
                        // Log the exception securely
                        LogException(ex);
                    }
                    catch (Exception ex)
                    {
                        Console.WriteLine($"Account creation failed: {ex.Message}");
                        // Log the exception securely
                        LogException(ex);
                    }
                    finally
                    {
                        // Any cleanup code would go here.
                    }
                }
                return accounts;
            }
            static async Task SimulateTransactionsAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                var tasks = accounts.Select(async account =>
                {
                    for (int i = 0; i < numberOfTransactions; i++)
                    {
                        double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                        try
                        {
                            account.Authenticate(account.Username, account.Password); // Authenticate before transaction
                            if (transactionAmount >= 0)
                            {
                                account.Credit(transactionAmount);
                                Console.WriteLine($"Credit: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                            }
                            else
                            {
                                account.Debit(-transactionAmount);
                                Console.WriteLine($"Debit: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                            }
                        }
                        catch (InvalidCreditAmountException ex)
                        {
                            Console.WriteLine($"Invalid credit amount: {ex.Message}");
                            LogException(ex);
                        }
                        catch (InvalidDebitAmountException ex)
                        {
                            Console.WriteLine($"Invalid debit amount: {ex.Message}");
                            LogException(ex);
                        }
                        catch (InsufficientFundsException ex)
                        {
                            Console.WriteLine($"Insufficient funds: {ex.Message}");
                            LogException(ex);
                        }
                        catch (AuthenticationException ex)
                        {
                            Console.WriteLine($"Authentication failed: {ex.Message}");
                            LogException(ex);
                        }
                        catch (Exception ex)
                        {
                            Console.WriteLine($"Transaction failed: {ex.Message}");
                            LogException(ex);
                        }
                    }
                    Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                });
                await Task.WhenAll(tasks);
            }
            static async Task SimulateTransfersAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                var tasks = accounts.Select(async account =>
                {
                    for (int i = 0; i < numberOfTransactions; i++)
                    {
                        double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                        try
                        {
                            account.Authenticate(account.Username, account.Password); // Authenticate before transfer
                            BankAccount toAccount = accounts[random.Next(accounts.Count)];
                            toAccount.Authenticate(toAccount.Username, toAccount.Password); // Authenticate target account
                            account.Transfer(toAccount, transactionAmount);
                            Console.WriteLine($"Transfer: {transactionAmount}, From: {account.AccountNumber}, To: {toAccount.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                        }
                        catch (InvalidTransferAmountException ex)
                        {
                            Console.WriteLine($"Invalid transfer amount: {ex.Message}");
                            LogException(ex);
                        }
                        catch (InsufficientFundsException ex)
                        {
                            Console.WriteLine($"Insufficient funds: {ex.Message}");
                            LogException(ex);
                        }
                        catch (AuthenticationException ex)
                        {
                            Console.WriteLine($"Authentication failed: {ex.Message}");
                            LogException(ex);
                        }
                        catch (Exception ex)
                        {
                            Console.WriteLine($"Transfer failed: {ex.Message}");
                            LogException(ex);
                        }
                    }
                    Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                });
                await Task.WhenAll(tasks);
            }
            static double GenerateRandomDollarAmount(bool isAccount, double min, double max)
            {
                if (isAccount)
                {
                    double accountStartingValue = random.NextDouble() * (max - min) + min;
                    return Math.Round(accountStartingValue, 2);
                }
                else
                {
                    double transactionAmount = random.NextDouble() * random.Next((int)min, (int)max) + random.NextDouble();
                    return Math.Round(transactionAmount, 2);
                }
            }
            static string GenerateRandomAccountHolder()
            {
                string[] accountHolderNames = { "John Smith", "Maria Garcia", "Mohammed Khan", "Sophie Dubois", "Liam Johnson", "Emma Martinez", "Noah Lee", "Olivia Kim", "William Chen", "Ava Wang", "James Brown", "Isabella Nguyen", "Benjamin Wilson", "Mia Li", "Lucas Anderson", "Charlotte Liu", "Alexander Taylor", "Amelia Patel", "Daniel Garcia", "Sophia Kim" };
                var accountHolderName = accountHolderNames[random.Next(0, accountHolderNames.Length)];
                return accountHolderName;
            }
            static string GenerateRandomAccountType()
            {
                string[] accountTypes = { "Savings", "Checking", "Money Market", "Certificate of Deposit", "Retirement" };
                return accountTypes[random.Next(0, accountTypes.Length)];
            }
            static DateTime GenerateRandomDateOpened()
            {
                DateTime startDate = new(DateTime.Today.Year - MaxYearsBack, 1, 1);
                int daysRange = (DateTime.Today - startDate).Days;
                DateTime randomDate = startDate.AddDays(random.Next(daysRange));
                if (randomDate.Year == DateTime.Today.Year && randomDate >= DateTime.Today)
                {
                    randomDate = randomDate.AddDays(-1);
                }
                return randomDate;
            }
            static string GenerateSecurePassword()
            {
                const int passwordLength = 12;
                const string validChars = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ1234567890!@#$%^&*()";
                StringBuilder password = new StringBuilder();
                using (RNGCryptoServiceProvider rng = new RNGCryptoServiceProvider())
                {
                    byte[] uintBuffer = new byte[sizeof(uint)];
                    while (passwordLength > password.Length)
                    {
                        rng.GetBytes(uintBuffer);
                        uint num = BitConverter.ToUInt32(uintBuffer, 0);
                        password.Append(validChars[(int)(num % (uint)validChars.Length)]);
                    }
                }
                return password.ToString();
            }
            static void LogException(Exception ex)
            {
                // Implement a secure logging mechanism here
                // For example, log to a file, database, or external logging service
                Console.WriteLine($"Logged exception: {ex.Message}");
            }
        }
    }

    ```

1. Implémentez les mises à jour suggérées qui aident à améliorer la sécurité du code pour votre fichier `Program.cs`.

1. Pour vous assurer qu’aucune erreur n’a été introduite par les modifications, compilez et exécutez votre solution.

## Résumé

Dans cette version de démonstration, vous avez utilisé GitHub Copilot Chat pour générer des suggestions pour améliorer la sécurité du code dans un exemple d’application. Vous avez développé des prompts qui ont dirigé GitHub Copilot pour fournir des suggestions visant à améliorer l’authentification, la protection des données, la journalisation et d’autres sujets liés à la sécurité. Vous avez implémenté les mises à jour suggérées pour améliorer la sécurité de la classe BankAccount et de la classe Program dans le projet **APL2007M5BankAccount-Security**.
