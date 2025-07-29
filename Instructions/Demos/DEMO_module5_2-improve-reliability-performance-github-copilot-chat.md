---
demo:
  title: "Démonstration\_: Améliorer la fiabilité et les performances du code à l’aide de GitHub Copilot Chat"
  module: 'Module 5: Implement code improvements using GitHub Copilot tools'
---

# Démonstration : Améliorer la fiabilité et les performances du code à l’aide de GitHub Copilot Chat

## Instructions

Les activités de la version de démonstration sont conçues pour un environnement qui inclut les ressources suivantes :

- Visual Studio Code.
- L’extension du kit de développement C# pour Visual Studio Code.
- Les extensions GitHub Copilot et GitHub Copilot Chat pour Visual Studio Code. Il est nécessaire de disposer d’un compte GitHub avec un abonnement actif pour GitHub Copilot.
- Des exemples de projets de code créés en C#.

**REMARQUE** : Nous recommandons aux instructeurs d’utiliser leur propre compte GitHub et leur abonnement GitHub Copilot pour les démonstrations. Ainsi vous pouvez contrôler et personnaliser votre environnement de développement. Cette démarche facilite également l’ajustement des démonstrations en fonction des besoins de vos salles de classe.

**IMPORTANT** : Si vous choisissez d’exécuter les démonstrations dans l’environnement de laboratoire hébergé plutôt que sur votre ordinateur personnel instructeur, vous pouvez décompresser les exemples d’applications dans l’environnement hébergé. Vous devez configurer les extensions GitHub Copilot dans l’environnement hébergé avant de pouvoir exécuter les démonstrations. Vous pouvez constater que l’environnement hébergé est plus lent que votre environnement local. Vous devrez probablement ajuster l’allure des démonstrations en conséquence.

### Présentez la version de démonstration

La fiabilité et le niveau de performance du code sont étroitement liés à la qualité des logiciels. Exemples d’interdépendances :

- L’optimisation de la fiabilité peut améliorer le niveau de performance du code et vice versa.
- Les lacunes en matière de fiabilité peuvent affecter le niveau de performance du code et vice versa.

> [!IMPORTANT]
> Expliquez aux étudiants que cette version de démonstration ne concerne pas les meilleures pratiques de développement de code fiable ou performant. Elle se concentre plutôt sur l’utilisation de GitHub Copilot Chat pour générer des suggestions visant à améliorer la fiabilité et le niveau de performance du code dans un exemple d’application. Ces suggestions ne sont ni des meilleures pratiques ni des solutions complètes pour garantir la fiabilité et le niveau de performance du code. Les développeurs doivent faire appel à leur bon sens et à leur expertise pour évaluer et mettre en œuvre les suggestions fournies par GitHub Copilot Chat. L’adoption des recommandations de GitHub Copilot ne remplace en aucun cas les processus de révision et de tests de code approfondis.

#### Fiabilité et performances du code

Les développeurs doivent viser un juste équilibre entre la fiabilité du code et ses performances. Un équilibre optimal engendre les bénéfices réciproques suivants :

- Les applications répondent aux exigences fonctionnelles.
- Les applications offrent une expérience utilisateur fluide et efficace.

Les sections suivantes fournissent une vue d’ensemble de la fiabilité et des performances du code, ainsi que d’autres facteurs que vos étudiants doivent connaître.

##### Vérifier la fiabilité du code

La fiabilité du code désigne la probabilité que les fonctionnalités d’un logiciel s’exécutent sans erreur dans des conditions définies et pendant une période donnée. Optimiser la fiabilité du code permet de s’assurer que votre logiciel fonctionne correctement et répond aux exigences des utilisateurs.

Les développeurs peuvent prendre en compte les facteurs suivants pour améliorer la fiabilité du code :

- Problèmes potentiels : Le repérage des éventuels problèmes dans le code peut prévenir l’émergence de bogues et d’erreurs. Au cours de cette procédure, il est recommandé de procéder à un examen du code afin d’identifier les problèmes courants et de les résoudre de manière proactive.
- Tests : Il est crucial d’exécuter des tests appropriés afin d’identifier et de rectifier les bogues avant le lancement du produit. Les tests suivants doivent être inclus : tests unitaires, tests d’intégration, tests système, tests d’acceptation.
- Gestion des exceptions : L’utilisation de mécanismes de gestion des exceptions appropriés permet de prévenir les défaillances du système en cas de conditions inattendues.

> [!NOTE]
> Assurez-vous d’atteindre une qualité de code élevée avant de vous concentrer sur sa fiabilité. La refactorisation du code, combinée au respect des normes et des directives, peut vous aider à garantir un code de haute qualité.

D’autres facteurs peuvent affecter la fiabilité du code. Si certains de ces facteurs ne relèvent pas des responsabilités des développeurs, d’autres doivent être pris en compte avant de travailler sur la fiabilité du code, ou après. Exemples de ces autres facteurs :

- Bonnes pratiques de développement : Appliquer les meilleures pratiques en matière de développement logiciel, telles que la révision du code, la programmation en binôme et l’adhésion aux normes de codage, peuvent conduire à un code plus fiable.
- Objectifs et métriques de fiabilité : Établir des objectifs de fiabilité précis et disposer de métriques pour les évaluer peut orienter le processus de développement vers la création de logiciels plus fiables.
- Documentation : Une documentation exhaustive peut favoriser la compréhension du système et de ses composants, un élément essentiel pour assurer la maintenance du système et résoudre les problèmes qui peuvent y survenir.
- Dépendances : Les bibliothèques et services externes dont dépend le code peuvent affecter sa fiabilité. L’échec d’un service tiers peut se propager et entraîner également l’échec du système dépendant.
- Performances : Les problèmes de performances peuvent également affecter la fiabilité. Il est primordial de garantir que le système fonctionne de manière fiable lorsqu’il est soumis à diverses charges.
- Surveillance et résolution de problèmes : Une surveillance continue et un guide de résolution des problèmes fiable peuvent accélérer l’identification et le traitement des problèmes, ce qui contribue à maintenir la fiabilité du service.
- Conception et architecture : Avec un système bien conçu et une architecture solide, il est possible de gérer les erreurs de manière adéquate tout en maintenant la disponibilité des fonctionnalités, même en cas d’échec de certains composants.
- Facteurs externes : Les problèmes de fiabilité peuvent survenir après la mise en production en raison de facteurs externes tels que les mises à jour du matériel et du système d’exploitation. Cela peut entraîner des problèmes de compatibilité ainsi que des défaillances système.

L’optimisation de la fiabilité de votre code peut vous aider à réduire la probabilité de rencontrer des bogues, des erreurs et des comportements inattendus.

##### Vérifier le niveau de performance du code

La performance du code désigne l’efficacité de l’exécution d’un programme ou d’une application, notamment en termes de vitesse, d’utilisation de la mémoire et de consommation globale des ressources. Pour garantir ou améliorer le niveau de performance du code, les développeurs peuvent effectuer plusieurs actions :

Les développeurs doivent considérer les facteurs suivants pour améliorer le niveau de performance du code :

- Optimiser les algorithmes : Choisissez les algorithmes et les structures de données les plus efficaces pour la tâche à accomplir. Même des améliorations mineures peuvent avoir un impact positif et significatif sur le niveau de performance.
- Éviter les calculs inutiles : Mettez en cache les résultats des opérations coûteuses lorsque cela est possible, et évitez les calculs redondants.
- Utiliser le multithreading et la programmation asynchrone : Tirez parti des architectures de processeur modernes en parallélisant les tâches et en traitant les opérations d’E/S de manière asynchrone.
- Minimiser les opérations d’entrée/sortie : Les opérations d’entrée/sortie de disque et de réseau peuvent être lentes. Il est donc important de réduire leur nombre ou de les exécuter de manière asynchrone pour éviter de bloquer le thread d’exécution principal.

> [!NOTE]
> Assurez-vous d’atteindre une qualité de code élevée avant de vous concentrer sur ses performances. La refactorisation du code, combinée au respect des normes et des directives, peut vous aider à garantir un code de haute qualité.

D’autres facteurs peuvent affecter le niveau de performance du code. Si certains de ces facteurs ne relèvent pas des responsabilités des développeurs, d’autres doivent être pris en compte avant de travailler sur le niveau de performance du code, ou après. Exemples de ces autres facteurs :

- Profil et évaluation : Utilisez des outils de profilage pour détecter les goulots d’étranglement liés aux performances. Procéder à une évaluation avant et après avoir apporté des modifications permet de mesurer l’impact des optimisations.
- Gérer efficacement la mémoire : Utilisez les outils de profilage de la mémoire pour détecter les fuites et garantir une allocation et une libération appropriées de la mémoire.
- Optimiser les interactions entre les bases de données : Pour réduire la surcharge sur les performances liée aux interactions avec la base de données, utilisez des requêtes efficaces et une indexation appropriée, et mettez en cache les données.
- Revues de code : Effectuez régulièrement des revues de code afin d’identifier d’éventuels problèmes de performance. Les évaluations par les pairs peuvent aider à repérer les inefficacités que le développeur d’origine aurait pu manquer.
- Suivre les mises à jour : Utilisez les dernières versions des langages, des bibliothèques et des frameworks, car elles intègrent souvent des améliorations relatives aux performances.
- Partager les connaissances et collaborer : Suivez l’évolution des meilleures pratiques en matière d’optimisation des performances, et collaborez avec d’autres développeurs pour tirer des enseignements de leurs expériences.

En se concentrant sur ces domaines, les développeurs peuvent grandement améliorer le niveau de performance du code qu’ils produisent pour créer des applications plus rapides et plus réactives. L’optimisation des performances est un processus continu. Il est essentiel de surveiller et d’améliorer en permanence le niveau de performance de vos applications.

GitHub Copilot Chat peut vous aider à améliorer le niveau de performance de votre code en fournissant des suggestions pour optimiser les algorithmes, réduire les calculs superflus, exploiter le multithreading et la programmation asynchrone, et minimiser les opérations d’entrée/sortie.

### Développer des prompts pour GitHub Copilot Chat

Les prompts que vous écrivez pour GitHub Copilot Chat doivent fournir un contexte et une intention clairement définis. Tenez compte des suggestions suivantes lors du développement de vos prompts :

- Définissez un contexte externe délimité à un niveau supérieur au code que vous souhaitez mettre à jour. Par exemple, si vous souhaitez améliorer une méthode, spécifiez la classe ou le fichier qui inclut la méthode comme contexte externe. Repérez la méthode comme contexte interne.
- Utilisez les participants de conversation et les variables de conversation pour vous aider à spécifier le contexte. Vous pouvez utiliser les variables de conversation `#file:` et `#selection` pour identifier le code spécifique sur lequel vous vous concentrez. Vous pouvez également inclure l’espace de travail complet (`@workspace`) le cas échéant. Reportez-vous à la sélection du fichier ou du code dans la partie en langage naturel de votre prompt.
- L’intention doit être claire, concise et spécifique. Votre prompt doit spécifier le type d’amélioration que vous souhaitez atteindre.

Au cours de cette phase de la version de démonstration, vous examinez le projet **APL2007M5BankAccount-Reliability** et créez trois requêtes pour GitHub Copilot Chat. Le prompt vise à améliorer la fiabilité et le niveau de performance du code.

Suivez les étapes ci-dessous pour effectuer cette phase de la version de démonstration :

1. Ouvrez l’exemple d’application **APL2007M5BankAccount-Reliability** dans Visual Studio Code.

1. Ouvrez la vue Explorateur de solutions.

1. Développez le projet **BankAccount**, puis examinez les fichiers de code **BankAccount.cs** et **Program.cs**.

    Le fichier **BankAccount.cs** contient le code de la classe `BankAccount`, qui représente un compte bancaire avec des propriétés telles que AccountNumber, Balance, AccountHolderName, AccountType et DateOpened. Vous y trouverez les méthodes suivantes :

    - Crédit(double amount) : Cette méthode augmente le solde du compte du montant spécifié.
    - Debit(double amount) : Cette méthode diminue le solde du compte du montant spécifié. Si le solde du compte est inférieur au montant spécifié, la méthode déclenche une exception avec le message « Solde insuffisant pour procéder au débit ».
    - GetBalance(): Cette méthode affiche le solde actuel du compte.
    - Transfer(BankAccount toAccount, double amount) : Cette méthode transfère un montant spécifié du compte actuel au compte toAccount. Si le solde du compte est inférieur au montant spécifié, la méthode déclenche une exception avec le message « Solde insuffisant pour procéder au transfert ». Si AccountHolderName est différent et que le montant est supérieur à 500, la méthode déclenche une exception avec le message « Le montant du transfert dépasse la limite de propriétaires de compte différents ».
    - PrintStatement() : Cette méthode publie AccountNumber et Balance dans la console.
    - CalculateInterest(double interestRate) : Cette méthode calcule le montant des intérêts sur le solde actuel à partir de la spécification d’interestRate.

    Le fichier **Program.cs** contient une application console qui simule un système bancaire. Il inclut les méthodes suivantes :

    - Méthode main : Le point d’entrée de l’application. Cette méthode crée une liste des comptes bancaires et simule les transactions et les transferts effectués sur ces comptes.
    - Méthode CreateBankAccounts : Cette méthode crée un nombre spécifié de comptes bancaires avec des soldes initiaux, des noms de titulaires de comptes, des types de comptes et des dates d’ouverture aléatoires. Elle utilise un bloc try-catch pour gérer les exceptions qui peuvent se produire lors de la création du compte.
    - Méthode SimulateTransactions : Cette méthode simule un nombre spécifié de transactions sur chaque compte de la liste fournie. Chaque transaction correspond à un montant de dollar aléatoire et peut être un crédit (dépôt) ou un débit (retrait), selon que le montant est positif ou négatif.
    - Méthode SimulateTransfers : Cette méthode est identique à la méthode SimulateTransactions. Elle semble conçue pour simuler des transferts entre comptes. Cependant, elle se contente actuellement de reproduire les fonctionnalités de SimulateTransactions.
    - Méthode GenerateRandomDollarAmount : Cette méthode génère un montant de dollar aléatoire dans une plage spécifiée. La méthode de portée et de calcul diffère selon que le montant correspond à un solde de compte ou à une transaction.
    - Méthode GenerateRandomAccountHolder : Cette méthode sélectionne un nom de titulaire de compte aléatoire dans une liste prédéfinie.
    - Méthode GenerateRandomAccountType : Cette méthode sélectionne un type de compte aléatoire à partir d’une liste prédéfinie.
    - Méthode GenerateRandomDateOpened : Cette méthode génère une date aléatoire dans une plage spécifiée pour la date d’ouverture du compte.

1. Prenez une minute pour décrire les requêtes qui pourraient vous aider à améliorer la fiabilité et les performances du code.

    Développez des prompts pour la classe BankAccount et la classe Program. Prenez en compte les facteurs de fiabilité et de niveau de performance suivants lors du développement de vos prompts :

    - Problèmes potentiels : Le repérage des éventuels problèmes dans le code peut prévenir l’émergence de bogues et d’erreurs. Cela inclut l’examen du code afin d’identifier les problèmes courants et de les résoudre de manière proactive.
    - Tests : Il est crucial d’exécuter des tests appropriés afin d’identifier et de rectifier les bogues avant le lancement du produit. Cela inclut les tests unitaires, les tests d’intégration, les tests système et les tests d’acceptation.
    - Gestion des exceptions : L’utilisation de mécanismes de gestion des exceptions appropriés permet de prévenir les défaillances du système en cas de conditions inattendues.

    - Optimiser les algorithmes : Choisissez les algorithmes et les structures de données les plus efficaces pour la tâche à accomplir. Même des améliorations mineures peuvent avoir un impact positif et significatif sur le niveau de performance.
    - Éviter les calculs inutiles : Mettez en cache les résultats des opérations coûteuses lorsque cela est possible, et évitez les calculs redondants.
    - Utilisez le multithreading et la programmation asynchrone : Tirez parti des architectures de processeur modernes en parallélisant les tâches et en traitant les opérations d’E/S de manière asynchrone.
    - Minimiser les opérations d’entrée/sortie : Les opérations d’entrée/sortie de disque et de réseau peuvent être lentes. Il est donc important de réduire leur nombre ou de les exécuter de manière asynchrone pour éviter de bloquer le thread d’exécution principal.

    Pour ce projet, vous pouvez utiliser les prompts suivants afin de générer des suggestions d’amélioration de la fiabilité de votre code :

    Requête : `@workspace /explain How can I improve exception handling the [selected code]?` (attacher BankAccount.cs au contexte Conversation)

    Requête : `@workspace /explain How can I reduce unexpected issues for the [selected code]?` (attacher BankAccount.cs au contexte Conversation)

    Requête : `@workspace /explain How can I improve unit test support for the [selected code]?` (attacher BankAccount.cs au contexte Conversation)

    Requête : `@workspace /explain How can I avoid future bugs or issues in the [selected code]?` (attacher Program.cs au contexte Conversation)

    Requête : `@workspace /explain How can I improve exception handling for the [selected code]?` (attacher Program.cs au contexte Conversation)

    Requête : `@workspace /explain How can I improve the efficiency of algorithms or data structures for the [selected code]?` (attacher Program.cs au contexte Conversation)

    Requête : `@workspace /explain How can I improve performance with asynchronous tasks or methods in the [selected code]?` (attacher Program.cs au contexte Conversation)

    Requête : `@workspace /explain How can I improve unit test support for the [selected code]?` (attacher BankAccountTests.cs et BankAccount.cs au contexte Conversation)

1. Sélectionnez deux requêtes que vous pouvez utiliser pour améliorer la classe BankAccount pendant cette version de démonstration.

    Pour la classe BankAccount, veillez à sélectionner des prompts axés sur la fiabilité.

1. Sélectionnez deux requêtes que vous pouvez utiliser pour améliorer la classe Program pendant cette version de démonstration.

    Pour la classe Program, veillez à sélectionner un prompt axé sur la fiabilité et un autre axé sur les performances.

### Améliorer la fiabilité et le niveau de performance de la classe BankAccount à l’aide de GitHub Copilot Chat

La fiabilité du code de production est un élément crucial dans tout projet logiciel. L’exemple d’application APL2007M5BankAccount-Reliability utilise la classe Program pour simuler le scénario bancaire, mais c’est la classe BankAccount qui est déployée dans un environnement de production. Améliorer la fiabilité du code permet d’assurer le bon fonctionnement de la classe BankAccount et de répondre aux exigences des utilisateurs.

GitHub Copilot Chat peut être utilisé pour améliorer la fiabilité de votre code. Vos prompts peuvent orienter GitHub Copilot pour générer des suggestions visant à améliorer la gestion des exceptions, à limiter les risques que des problèmes inattendus se produisent, et à renforcer la prise en charge des tests unitaires. Vous pouvez également créer des prompts de grande ampleur qui sollicitent des suggestions globales pour améliorer la fiabilité du code. L’utilisation d’une combinaison de prompts spécifiques et généraux peut vous aider à cibler les domaines nécessitant des améliorations et à mettre en œuvre les modifications nécessaires.

> [!NOTE]
> L’implémentation et le test des mises à jour suggérées prennent un certain temps. Ce facteur doit être pris en compte dans le cadre de cette version de démonstration. La sélection de prompts axés sur des domaines spécifiques d’amélioration peut vous aider à gérer votre temps. Les prompts dont l’ampleur est trop grande peuvent engendrer de nombreuses suggestions, voire des propositions complexes, rendant leur évaluation et leur mise en œuvre ardues dans des délais restreints. Une fois créés, vos prompts peuvent être mis à jour avec des détails plus spécifiques si vous remarquez que les mises à jour suggérées sont trop vastes ou trop complexes.

Suivez les étapes ci-dessous pour effectuer cette phase de la version de démonstration :

1. Vérifiez que le projet génère et s’exécute sans erreur.

    Les avertissements sont tolérables tant que l’application s’exécute, mais les erreurs non traitées entraînant le blocage de l’application doivent être résolues avant de commencer à utiliser GitHub Copilot Chat.

1. Ouvrez le fichier BankAccount.cs dans Visual Studio Code, puis sélectionnez tout le code dans le fichier.

1. Ouvrez la vue Conversation.

1. Dans l’affichage Conversation, ajoutez des fichiers pertinents au contexte de conversation, puis entrez votre invite.

1. Vérifiez les suggestions fournies par GitHub Copilot Chat.

    Par exemple, supposons que vous effectuiez les actions suivantes :

    - Vous ouvrez le fichier BankAccount.cs et vous sélectionnez tout le code.
    - Vous choisissez l’invite suivante : `@workspace /explain How can I improve exception handling in the BankAccount.cs file?`
    - Vous ouvrez la vue Conversation et vous attachez les fichiers BankAccount.cs et Program.cs au contexte Conversation.
    - Vous entrez l’invite dans la vue Conversation.

    Dans ce cas, GitHub Copilot Chat suggère des mises à jour semblables à la réponse suivante :

    *Pour améliorer le traitement des exceptions dans le fichier BankAccount.cs, tenez compte des suggestions suivantes :*

    *1. **Utilisez des exceptions spécifiques** : Plutôt que de lever la classe d’exception de base `Exception`, utilisez des exceptions plus spécifiques. Cette approche facilite la compréhension et la gestion des types d’erreurs spécifiques du code appelant. Par exemple, vous pouvez lever une exception InvalidOperationException lorsqu’une tentative de débit ou de transfert est faite sans fonds suffisants.*

    *2. **Incluez plus d’informations dans les messages d’exception** : Les messages d’exception peuvent fournir plus de détails sur l’opération qui a échoué. Par exemple, dans la méthode `Debit`, le message d’exception peut inclure le montant de la tentative de débit et le solde actuel.*

    *3. **Considérez les exceptions personnalisées** : Si votre application est soumise à des conditions d’erreur spécifiques, il est recommandé de créer des classes d’exception personnalisées. La création d’exceptions personnalisées vous permet d’encapsuler davantage d’informations sur la condition d’erreur, ce qui enrichit automatiquement la documentation de votre code.*

    *Voici comment améliorer la méthode `Debit` avec ces suggestions :*

    ```csharp

    public void Debit(double amount)
    {
        if (Balance >= amount)
        {
            Balance -= amount;
        }
        else
        {
            throw new InvalidOperationException($"Insufficient balance for debit. Attempted to debit {amount}, but current balance is {Balance}.");
        }
    }

    ```

    *Et voici un exemple de classe d’exception personnalisée :*

    ```csharp

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

    ```

    *Vous pouvez ensuite déclencher cette exception personnalisée dans la méthode Debit :*

    ```csharp

    public void Debit(double amount)
    {
        if (Balance >= amount)
        {
            Balance -= amount;
        }
        else
        {
            throw new InsufficientFundsException(amount, Balance);
        }
    }

    ```

    *Ainsi, le code appelant peut intercepter l’exception InsufficientFundsException et accéder aux propriétés AttemptedAmount et CurrentBalance, ce qui lui permet de gérer la condition d’erreur de manière plus efficace.*

1. Intégrez les mises à jour suggérées pour améliorer la fiabilité du code de votre classe `BankAccount`.

1. Pour vous assurer qu’aucune erreur n’a été introduite par les modifications, compilez et exécutez votre solution avant de continuer.

    > [!TIP]
    > Dans l’exemple ci-dessus, la vue Chat fournit des extraits de code qui intègrent un exemple de la mise à jour suggérée (en utilisant des exceptions spécifiques avec des informations supplémentaires sur le message d'exception, et en créant des exceptions personnalisées). Après avoir intégré les suggestions, essayez d’utiliser des saisies semi-automatiques de ligne de code pour générer un nouveau code qui duplique la mise à jour. Pour cet exemple, les fonctionnalités d’auto-complétion de code peuvent être employées afin de générer des classes d’exception plus personnalisées. Ensuite, vous pouvez utiliser les fonctionnalités d’auto-complétion de code pour mettre à jour les autres méthodes avec les nouvelles exceptions personnalisées. Vous pouvez également réexécuter le prompt d’origine pour afficher d’autres suggestions.

1. Sélectionnez tout le code dans le fichier BankAccount.cs.

1. Ouvrez la vue Conversation.

1. Utilisez le bouton **Attacher le contexte** pour ajouter des fichiers pertinents au contexte Conversation, puis entrez votre deuxième requête « fiabilité ».

1. Vérifiez les suggestions fournies par GitHub Copilot Chat.

    Par exemple, si vous entrez `@workspace /explain How can I reduce unexpected issues for the selected code?` dans la vue Conversation, GitHub Copilot Chat suggère des mises à jour similaires à la réponse suivante :

    *Pour réduire les problèmes inattendus dans la classe BankAccount, vous pouvez implémenter les améliorations suivantes :*

    *1. Utiliser l’énumération pour le type de compte : Plutôt que d’utiliser une chaîne pour le type de compte en vérifiant s’il s’agit du compte « Épargne » ou « Courant », envisagez d’utiliser une énumération. Cette méthode limite les risques de rencontrer des problèmes potentiels associés à la comparaison de chaînes, comme le respect de la casse, tout en restreignant le type de compte aux valeurs prédéfinies.*

    ```csharp

    public enum AccountType
    {
        Savings,
        Current
    }

    ```

    *2. Utiliser une décimale pour les valeurs monétaires : Pour éviter les erreurs d’arrondi, il est généralement recommandé d’utiliser le type décimal au lieu du type double pour les valeurs monétaires.*

    *3. Ajouter d’autres validations : Vous pouvez ajouter d’autres validations dans vos méthodes. Par exemple, dans la méthode Transfer, vous pouvez vérifier si le toAccount n’est pas nul avant de poursuivre le transfert.*

    *4. Utiliser des constantes à la place des valeurs magiques : Dans votre méthode Transfert, la valeur magique 500 est utilisée en dur. Il serait préférable de la définir comme une constante, avec un nom explicite, en haut de votre classe.*

    ```csharp
    private const double MaxTransferAmountForDifferentOwners = 500;
    ```

    *5. Exception personnalisée pour la limite de transfert : Au lieu de déclencher une exception générale lorsque le montant du transfert la limite de propriétaires de compte différents, envisagez de créer une exception personnalisée comme ExceededTransferLimitException.*

    *6. Journalisation : Envisagez d’ajouter une journalisation supplémentaire à votre application. Cette solution peut vous aider à suivre le déroulement du programme et à diagnostiquer d’éventuels problèmes.*

    *7. Tests unitaires : Écrivez des tests unitaires pour vos méthodes afin de vérifier qu’elles se comportent correctement dans différents scénarios. Cette approche permet de détecter les erreurs plus tôt dans le processus de développement.*

1. Prenez en compte la portée et l’ampleur des suggestions fournies par GitHub Copilot Chat.

    Certains prompts peuvent générer un grand nombre de suggestions qui ont un large impact. Si cela se produit, examinez la possibilité de n’utiliser qu’un seul élément de suggestion pour définir un nouveau prompt avec une intention et/ou un contexte plus spécifiques.

1. Utilisez la liste des suggestions pour concevoir un prompt avec une intention et/ou un contexte plus détaillés.

    Chacune des suggestions fournies par GitHub Copilot Chat peut être examinée et implémentée séparément. En traitant la liste de haut en bas, vous pouvez vous concentrer sur une amélioration à la fois.

1. Entrez votre prompt détaillé dans la vue Chat, puis examinez les suggestions fournies par GitHub Copilot Chat.

    Supposons que vous utilisiez le deuxième exemple de prompt sur la fiabilité. La réponse de GitHub Copilot Chat comprend l’élément de suggestion suivant :

    *Ajouter d’autres validations : Vous pouvez ajouter d’autres validations dans vos méthodes. Par exemple, dans la méthode Transfer, vous pouvez vérifier si le toAccount n’est pas nul avant de poursuivre le transfert.*

    Vous pouvez utiliser cette suggestion pour créer un prompt qui se concentre sur l’ajout de validations supplémentaires à la méthode Transfer. Vous pouvez sélectionner la méthode Transfer, puis entrer le prompt suivant dans la vue Chat :

    `@workspace /explain #file:BankAccount.cs How can I improve method validations for the selected code?`

    Dans ce cas, GitHub Copilot Chat suggère des mises à jour semblables à la réponse suivante :

    *Le code que vous avez fourni est bien structuré et suit les meilleures pratiques pour la gestion des exceptions. Toutefois, il existe quelques domaines où vous pouvez apporter des améliorations :*

    *1. Consolider la logique de validation : Vous pouvez créer une classe ou une méthode de validation distincte pour gérer toute la logique de validation. Cela rend votre classe BankAccount plus claire et mieux recentrée sur ses responsabilités principales.*

    *2. Utilisez des attributs de validation personnalisés : Pour certaines des validations, vous pouvez utiliser des attributs de validation personnalisés. Ainsi vous pourrez annoter les propriétés qui ont besoin de validation et séparer la logique de validation de la logique métier.*

    *3. Utiliser Fluent Validation : Fluent Validation est une bibliothèque .NET qui utilise une interface Fluent et des expressions lambda pour générer des règles de validation. Elle peut rendre votre code de validation plus intuitif et plus lisible.*

    *4. Évitez les valeurs magiques : Dans votre méthode Transfer, vous avez une valeur codée en dur de 500. Les « valeurs magiques » sont généralement déconseillées. Il est préférable de les définir en tant que constantes avec des noms explicites en haut de votre classe.*

    Voici un exemple de mise en œuvre pour certaines de ces suggestions :

    ```csharp

    public class BankAccount
    {
        private const double MaxTransferAmountForDifferentOwners = 500;
        // ...
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
            if (AccountHolderName != toAccount.AccountHolderName && amount > MaxTransferAmountForDifferentOwners)
            {
                throw new Exception("Transfer amount exceeds maximum limit for different account owners.");
            }
        }
    }

    ```

    Vous pouvez continuer à traiter les suggestions fournies par GitHub Copilot Chat afin d’appliquer toutes les améliorations que vous jugez nécessaires.

1. Appliquez les mises à jour suggérées, puis compilez et exécutez votre solution avant de continuer.

    Corrigez les erreurs introduites par les modifications, puis continuez.

### Améliorer la fiabilité et le niveau de performance du code de la classe Program à l’aide de GitHub Copilot Chat

1. Ouvrez le fichier Program.cs dans Visual Studio Code, puis sélectionnez tout le code dans le fichier.

1. Ouvrez le fichier Program.cs dans Visual Studio Code, puis sélectionnez tout le code dans le fichier.

1. Ouvrez la vue Conversation.

1. Dans la vue Conversation, utilisez le bouton **Attacher le contexte** pour ajouter des fichiers pertinents au contexte Conversation, puis entrez votre requête.

1. Vérifiez les suggestions fournies par GitHub Copilot Chat.

    Par exemple, si vous entrez `@workspace /explain How can I improve performance with asynchronous tasks or methods in the Program.cs file?` dans la vue Conversation, GitHub Copilot Chat suggère des mises à jour similaires à la réponse suivante :

    *Pour améliorer les performances avec des méthodes ou tâches asynchrones dans le fichier Program.cs, vous pouvez utiliser la programmation asynchrone avec les mots clés async et await. Cette opération autorise le programme à effectuer des opérations liées aux E/S sans bloquer la conversation principale, ce qui la rend plus efficace et réactive.*

    *Voici une version améliorée du fichier Program.cs avec des méthodes asynchrones :*

    ```csharp

    using System;
    using System.Collections.Generic;
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
            static async Task Main(string[] args)
            {
                List<BankAccount> accounts = await CreateBankAccountsAsync(NumberOfAccounts);
                await SimulateTransactionsAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
                await SimulateTransfersAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
            }
            static async Task<List<BankAccount>> CreateBankAccountsAsync(int numberOfAccounts)
            {
                List<BankAccount> accounts = new List<BankAccount>();
                int createdAccounts = 0;
                while (createdAccounts < numberOfAccounts)
                {
                    try
                    {
                        double initialBalance = GenerateRandomDollarAmount(true, minAccountStart, maxAccountStart);
                        string accountHolderName = GenerateRandomAccountHolder();
                        string accountType = GenerateRandomAccountType();
                        DateTime dateOpened = GenerateRandomDateOpened();
                        BankAccount account = new BankAccount($"Account {createdAccounts + 1}", initialBalance, accountHolderName, accountType, dateOpened);
                        accounts.Add(account);
                        createdAccounts++;
                    }
                    catch (Exception ex)
                    {
                        Console.WriteLine($"Account creation failed: {ex.Message}");
                    }
                    await Task.Yield(); // Yield control to allow other tasks to run
                }
                return accounts;
            }
            static async Task SimulateTransactionsAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                List<Task> tasks = new List<Task>();
                foreach (BankAccount account in accounts)
                {
                    tasks.Add(Task.Run(async () =>
                    {
                        for (int i = 0; i < numberOfTransactions; i++)
                        {
                            double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                            try
                            {
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
                            await Task.Yield(); // Yield control to allow other tasks to run
                        }
                        Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                    }));
                }
                await Task.WhenAll(tasks);
            }
            static async Task SimulateTransfersAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                List<Task> tasks = new List<Task>();
                foreach (BankAccount account in accounts)
                {
                    tasks.Add(Task.Run(async () =>
                    {
                        for (int i = 0; i < numberOfTransactions; i++)
                        {
                            double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                            try
                            {
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
                            await Task.Yield(); // Yield control to allow other tasks to run
                        }
                        Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                    }));
                }
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
                DateTime startDate = new DateTime(DateTime.Today.Year - MaxYearsBack, 1, 1);
                int daysRange = (DateTime.Today - startDate).Days;
                DateTime randomDate = startDate.AddDays(random.Next(daysRange));
                if (randomDate.Year == DateTime.Today.Year && randomDate >= DateTime.Today)
                {
                    randomDate = randomDate.AddDays(-1);
                }
                return randomDate;
            }
        }
    }

    ```

1. Intégrez les mises à jour suggérées pour améliorer le niveau de performance (ou la fiabilité) du code de votre classe `Program`.

1. Pour vous assurer qu’aucune erreur n’a été introduite par les modifications, compilez et exécutez votre solution avant de continuer.

1. Sélectionnez tout le code dans le fichier Program.cs, puis entrez votre prompt « fiabilité » dans la vue Chat.

1. Examinez les suggestions fournies par GitHub Copilot Chat.

    > [!NOTE]
    > Vous n’avez pas besoin d’appliquer les suggestions de mise à jour générées par GitHub Copilot à partir de ce quatrième prompt, mais vous devez les passer en revue.

    Par exemple, si vous entrez `@workspace /explain How can I improve exception handling for the selected code?` dans la vue Chat, GitHub Copilot Chat suggère des mises à jour semblables à la réponse suivante :

    *Pour améliorer le traitement des exceptions dans le fichier Program.cs, vous pouvez implémenter les suggestions suivantes :*

    *1. Utilisez les types d’exceptions spécifiques : Au lieu d’intercepter une exception générique, interceptez des exceptions spécifiques lorsque cela est possible.*

    *2. Ajouter davantage de contexte aux exceptions : Fournissez davantage de contexte dans les messages d’exception pour faciliter le débogage.*

    *3. Exceptions liées aux journaux : Au lieu d’imprimer simplement des exceptions dans la console, envisagez de les journaliser pour une meilleure traçabilité.*

    *Voici une version améliorée du fichier Program.cs avec un meilleur traitement des exceptions :*

    ```csharp

    using System;
    using System.Collections.Generic;
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
            static async Task Main(string[] args)
            {
                List<BankAccount> accounts = await CreateBankAccountsAsync(NumberOfAccounts);
                await SimulateTransactionsAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
                await SimulateTransfersAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
            }
            static async Task<List<BankAccount>> CreateBankAccountsAsync(int numberOfAccounts)
            {
                List<BankAccount> accounts = new List<BankAccount>();
                int createdAccounts = 0;
                while (createdAccounts < numberOfAccounts)
                {
                    try
                    {
                        double initialBalance = GenerateRandomDollarAmount(true, minAccountStart, maxAccountStart);
                        string accountHolderName = GenerateRandomAccountHolder();
                        string accountType = GenerateRandomAccountType();
                        DateTime dateOpened = GenerateRandomDateOpened();
                        BankAccount account = new BankAccount($"Account {createdAccounts + 1}", initialBalance, accountHolderName, accountType, dateOpened);
                        accounts.Add(account);
                        createdAccounts++;
                    }
                    catch (ArgumentException ex)
                    {
                        Console.WriteLine($"Account creation failed due to invalid argument: {ex.Message}");
                    }
                    catch (Exception ex)
                    {
                        Console.WriteLine($"Account creation failed: {ex.Message}");
                    }
                    await Task.Yield(); // Yield control to allow other tasks to run
                }
                return accounts;
            }
            static async Task SimulateTransactionsAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                List<Task> tasks = new List<Task>();
                foreach (BankAccount account in accounts)
                {
                    tasks.Add(Task.Run(async () =>
                    {
                        for (int i = 0; i < numberOfTransactions; i++)
                        {
                            double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                            try
                            {
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
                            catch (ArgumentException ex)
                            {
                                Console.WriteLine($"Transaction failed due to invalid argument: {ex.Message}");
                            }
                            catch (InsufficientBalanceException ex)
                            {
                                Console.WriteLine($"Transaction failed due to insufficient balance: {ex.Message}");
                            }
                            catch (Exception ex)
                            {
                                Console.WriteLine($"Transaction failed: {ex.Message}");
                            }
                            await Task.Yield(); // Yield control to allow other tasks to run
                        }
                        Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                    }));
                }
                await Task.WhenAll(tasks);
            }
            static async Task SimulateTransfersAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                List<Task> tasks = new List<Task>();
                foreach (BankAccount account in accounts)
                {
                    tasks.Add(Task.Run(async () =>
                    {
                        for (int i = 0; i < numberOfTransactions; i++)
                        {
                            double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                            try
                            {
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
                            catch (ArgumentException ex)
                            {
                                Console.WriteLine($"Transaction failed due to invalid argument: {ex.Message}");
                            }
                            catch (InsufficientBalanceException ex)
                            {
                                Console.WriteLine($"Transaction failed due to insufficient balance: {ex.Message}");
                            }
                            catch (Exception ex)
                            {
                                Console.WriteLine($"Transaction failed: {ex.Message}");
                            }
                            await Task.Yield(); // Yield control to allow other tasks to run
                        }
                        Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                    }));
                }
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
                DateTime startDate = new DateTime(DateTime.Today.Year - MaxYearsBack, 1, 1);
                int daysRange = (DateTime.Today - startDate).Days;
                DateTime randomDate = startDate.AddDays(random.Next(daysRange));
                if (randomDate.Year == DateTime.Today.Year && randomDate >= DateTime.Today)
                {
                    randomDate = randomDate.AddDays(-1);
                }
                return randomDate;
            }
        }
    }

    ```

## Résumé

Dans cette version de démonstration, vous avez utilisé GitHub Copilot Chat pour générer des suggestions visant à améliorer la fiabilité et le niveau de performance du code dans un exemple d’application. Vous avez conçu des prompts qui peuvent orienter GitHub Copilot pour fournir des suggestions visant à améliorer la gestion des exceptions, à limiter les risques que des problèmes inattendus se produisent, et à renforcer la prise en charge des tests unitaires. Vous avez également créé des prompts axés sur l’amélioration des performances avec des tâches ou des méthodes asynchrones.
