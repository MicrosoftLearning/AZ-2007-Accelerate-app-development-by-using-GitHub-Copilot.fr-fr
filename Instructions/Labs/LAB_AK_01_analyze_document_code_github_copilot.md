---
lab:
  title: "Labo\_: accélérer le développement d’applications à l’aide de GitHub\_Copilot"
  type: Answer Key
  module: Modules 2-5
---

# Labo : accélérer le développement d’applications à l’aide de GitHub Copilot
# Labo étudiant - Corrigé

## Partie 1 : analyser et documenter du code à l’aide des outils GitHub Copilot

### Avant de commencer

#### Vue d'ensemble du projet

Vous êtes un développeur de logiciels travaillant pour un service informatique régional. La plupart des applications sur lesquelles vous travaillez prennent en charge la communauté locale. Récemment, les serveurs de la bibliothèque ont été endommagés dans un accident et il faudra des semaines pour obtenir l’autorisation de les remplacer. Votre département doit développer une solution temporaire qui permettra aux bibliothécaires d’effectuer des fonctions de base.

Votre équipe a rencontré les bibliothécaires en question. Ils ont besoin d’une solution qui leur permet au moins de fournir aux adhérents des services de base tels que le prêt et le retour de livres. Votre équipe examine les ressources disponibles et développe un plan. Au départ, seul vous et un autre collègue êtes affectés au projet. L’administration locale a fermé la bibliothèque tant que votre solution temporaire n’est pas disponible. Vous avez trois jours pour développer la version 1 de la solution qui permettra à la bibliothèque de rouvrir.

Alors que votre collègue commence à travailler sur le logiciel, vous utilisez les archives de la bibliothèque pour créer des fichiers JSON qui représentent les comptes des adhérents, les livres et les prêts de livres de la bibliothèque. Au terme du deuxième jour, vous êtes prêt à commencer à aider sur le code. La solution est une application console qui peut être exécutée sur l’un des ordinateurs portables de la bibliothèque. Les bibliothécaires comprennent que le temps manque pour avoir une interface agréable, mais insistent sur le fait que l’application doit être sécurisée et fiable. Il vous reste un jour avant de devoir montrer la version 1.0 de votre application.

Vous allez utiliser GitHub Copilot pour vous aider à réaliser le travail aussi efficacement que possible. Si tout va bien, votre application sera utilisée pour prendre en charge la collecte de livres de la bibliothèque et d’autres fonctions en dehors du site.

#### Scénario de labo (partie 1)

GitHub Copilot peut vous aider à comprendre et à documenter un codebase en générant des explications et de la documentation.

Dans la partie 1 de ce labo, vous allez utiliser GitHub Copilot pour analyser et documenter l’application de bibliothèque. Vous allez également créer un dépôt GitHub pour l’application de bibliothèque et générer un fichier README pour le dépôt à l’aide de GitHub Copilot.

La partie 1 comprend les exercices suivants :

- Configurer des extensions GitHub Copilot pour Visual Studio Code.
- Utiliser GitHub Copilot pour expliquer le codebase de l’application de bibliothèque.
- Utiliser Visual Studio Code pour créer un dépôt GitHub pour l’application de bibliothèque.
- Utiliser des extensions GitHub Copilot pour créer un fichier README.md pour le référentiel.

### Exercice 1 : configurer des extensions GitHub Copilot pour Visual Studio Code

Vous allez utiliser votre compte GitHub pour autoriser Visual Studio Code à vérifier votre abonnement GitHub Copilot.

Pour installer les extensions GitHub Copilot, procédez de la manière suivante :

1. Ouvrez une fenêtre de navigateur.

1. Pour ouvrir le portail GitHub Enterprise, accédez à l’URL suivante :

    ```plaintext
    https://github.com/enterprises/Microsoft-APL/sso
    ```

1. Connectez-vous à votre compte GitHub à l’aide des informations d’identification suivantes :

    E-mail/Nom d’utilisateur :`@lab.CloudPortalCredential(1).Username`

    Mot de passe : `@lab.CloudPortalCredential(1).Password`

1. Ouvrez Visual Studio Code.

1. Dans le menu de gauche, sélectionnez **Extensions**.

1. Dans la zone de texte Rechercher des extensions de la Place de marché, tapez **GitHub Copilot** , puis appuyez sur Entrée.

1. Dans la liste filtrée des extensions, sélectionnez l’extension **GitHub Copilot** créée par GitHub.

1. Sur la page de l’extension GitHub Copilot, sélectionnez **Installer**.

1. Lorsque vous êtes invité à vous connecter pour utiliser GitHub Copilot, sélectionnez **Se connecter à GitHub**.

    Si vous voyez une boîte de dialogue indiquant que GitHub Copilot souhaite se connecter à l’aide de GitHub, sélectionnez **Autoriser**.

    Étant donné que vous êtes déjà connecté à votre compte GitHub dans une fenêtre de navigateur, un nouvel onglet Vérifier la session doit s’ouvrir dans votre fenêtre de navigateur.

1. Dans la page Vérifier la session, sélectionnez **Continuer**.

1. Sur la page Autoriser l’application, sélectionnez **Authoriser Visual Studio**.

1. Sélectionnez **Ouvrir** pour revenir dans Visual Studio Code.

1. Fermez Visual Studio Code, puis rouvrez-le.

    Le redémarrage de Visual Studio Code permet de s’assurer que GitHub Copilot est intégré à l’interface utilisateur de Visual Studio Code.

1. Notez que le bouton **Ouvrir la conversation** est désormais visible sur le côté droit du Centre de commandes en haut de la fenêtre Visual Studio Code.

#### Résumé - Exercice 1

Dans cet exercice, vous allez installé l’extension GitHub Copilot pour Visual Studio Code. Vous avez aussi autorisé Visual Studio Code à accéder à votre compte GitHub. Vous êtes maintenant prêt à utiliser GitHub Copilot pour analyser et documenter le codebase de l’application de bibliothèque.

### Exercice 2 : analyser le codebase de l’application de bibliothèque

Avant de créer un dépôt de code et un fichier README, vous devez consacrer un moment à examiner le codebase. Il est important de comprendre l’architecture et les fonctionnalités clés de l’application avant de documenter le projet. Vous devez également exécuter l’application afin de vérifier qu’elle s’exécute comme prévu.

#### Tâche 1 : charger l’application de bibliothèque dans votre environnement de développement

Votre collègue a développé une première version de l’application de la bibliothèque et l’a mise à disposition sous la forme d’un fichier .zip. Pour vous préparer à ce labo, vous devez effectuer les actions suivantes :

- Téléchargez un fichier zip contenant la solution.
- Extrayez les fichiers de code.
- Ouvrez l’application de bibliothèque dans Visual Studio Code et assurez-vous qu’elle est générée correctement.

Suivez les étapes ci-après pour préparer l’application de la bibliothèque :

1. Vérifiez que votre navigateur web est ouvert, puis ouvrez un nouvel onglet de navigateur.

1. Pour télécharger le fichier zip contenant votre projet de code, accédez à l’URL suivante :

    ```plaintext
    https://raw.githubusercontent.com/MicrosoftLearning/APL-2007-Accelerate-app-development-by-using-GitHub-Copilot/master/LearnModuleExercises/Downloads/GuidedProjectApp.zip
    ```

    Le fichier zip contenant le code de votre solution, GuidedProjectApp.zip, doit se télécharger automatiquement.

1. Une fois le téléchargement terminé, fermez l’onglet du navigateur.

    Gardez la page de navigateur de votre compte GitHub ouverte. Vous allez l’utiliser plus tard dans le labo.

1. Ouvrez l’Explorateur de fichiers Windows et accédez au dossier Téléchargements.

1. Décompressez les fichiers projet téléchargés.

    Décompressez le projet de code dans votre environnement de développement. Par exemple :

    1. Sur votre ordinateur local, accédez à votre dossier de téléchargements.

    1. Cliquez avec le bouton droit sur **GuidedProjectApp.zip**, puis sélectionnez **Tout extraire**.

    1. Cochez **Afficher les dossiers extraits une fois l’opération terminée**, puis sélectionnez **Extraire**.

    1. Notez l’emplacement du dossier extrait.

1. Copiez le dossier AccelerateDevGitHubCopilot extrait dans un endroit facile d’accès, tel que votre dossier Bureau Windows.

1. Ouvrez le dossier **AccelerateDevGitHubCopilot** dans Visual Studio Code.

    Par exemple :

    1. Ouvrez Visual Studio Code sur votre PC.

    1. Dans Visual Studio Code, dans le menu **Fichier**, sélectionnez **Ouvrir un dossier**.

    1. Accédez au dossier Bureau Windows et recherchez le dossier **AccelerateDevGitHubCopilot**.

    1. Sélectionnez **AccelerateDevGitHubCopilot**, puis **Sélectionner un dossier**.

    1. Sélectionnez **Oui, j’ai confiance dans les auteurs**.

    > [!NOTE]
    > Visual Studio Code peut mettre 10 à 20 secondes à charger les fichiers du projet et toutes les mises à jour .NET requises.

1. Dans la vue EXPLORATEUR de Visual Studio Code, sélectionnez EXPLORATEUR DE SOLUTIONS, puis vérifiez la structure de projet suivante :

    - AccelerateDevGitHubCopilot\
        - src\
            - Library.ApplicationCore\
            - Library.Console\
            - Library.Infrastructure\
        - tests\
            - UnitTests\

1. Assurez-vous que la solution se génère correctement.

    Par exemple, dans la vue EXPLORATEUR DE SOLUTIONS, cliquez avec le bouton droit sur **AccelerateDevGitHubCopilot**, puis sélectionnez **Générer**.

    Vous verrez plusieurs **avertissements**, mais il ne devrait y avoir aucune erreur. Vous allez exécuter l’application plus loin dans cet exercice.

    > [!NOTE]
    > N’installez pas les mises à jour de la charge de travail, sauf si votre instructeur vous invite à le faire.

#### Tâche 2 : utiliser GitHub Copilot pour expliquer le codebase de l’application de bibliothèque

GitHub Copilot peut vous aider à comprendre un codebase inconnu en générant des explications au niveau de la solution et des fonctionnalités.

Utilisez les étapes suivantes pour terminer cette section de l’exercice :

1. Vérifiez que la solution AccelerateDevGitHubCopilot est ouverte dans Visual Studio Code.

1. Ouvrez l’affichage Conversation.

    Vous pouvez ouvrir la vue Conversation de plusieurs manières :

    - Sélectionnez le bouton **Ouvrir une conversation** (en haut de la fenêtre Visual Studio Code, juste à droite du centre de commandes).
    - Utilisez le raccourci clavier **Ctrl+Alt+I**.
    - Ouvrez le menu d’état de GitHub Copilot, puis sélectionnez **GitHub Copilot Chat**.

1. Entrez un prompt qui utilise le participant **@workspace** de GitHub Copilot pour générer une description du projet.

    Par exemple, entrez le prompt suivant dans la vue Conversation :

    ```plaintext
    @workspace Describe this project
    ```

    Si vous voyez une boîte de dialogue Visual Studio Code indiquant que GitHub Copilot Chat souhaite se connecter à l’aide de GitHub, sélectionnez **Autoriser**, puis terminez le processus d’autorisation à l’aide de votre compte GitHub.

1. Prenez quelques instants pour passer en revue la réponse générée par GitHub Copilot.

    Vous devez voir une réponse similaire à la description suivante :

    ```markdown
    This project is a library management system implemented in C#. It consists of three main components:
    
    1. **Library.ApplicationCore**: This is the core application library containing the main business logic, entities, enums, and interfaces. It includes:
        - Entities such as Book, Patron, Loan, etc.
        - Enums like MembershipRenewalStatus, LoanReturnStatus, and LoanExtensionStatus.
        - Services like LoanService and PatronService.
        - Interfaces like ILoanRepository, IPatronRepository, ILoanService, and IPatronService.
    2. **Library.Console**: This is a console application that interacts with the user. It includes:
        - The main entry point in Program.cs.
        - Configuration settings in appSettings.json.
        - Console interaction logic in ConsoleApp.cs.
    3. **Library.Infrastructure**: This library handles data persistence. It includes:
        - JSON-based repositories like JsonPatronRepository and JsonLoanRepository.
        - Data loading and saving logic in JsonData.

    Additionally, there are unit tests located in the UnitTests directory, which test the functionality of the core services using the NSubstitute mocking framework and xUnit.
    
    The project uses .NET 8.0 and is configured to build and test using GitHub Actions as defined in the build-test.yml file. The solution file is AccelerateDevGitHubCopilot.sln, which includes all the projects and their configurations.
    ```

1. Utilisez la vue Explorateur de solutions de Visual Studio Code pour développer les dossiers du projet.

1. Recherchez et ouvrez le fichier **ConsoleApp.cs**.

    Le fichier ConsoleApp.cs se trouve dans le projet src/Library.Console.

1. Dans la vue Conversation, entrez un prompt qui génère une description de la classe ConsoleApp.

    Par exemple, entrez le prompt suivant dans la vue Conversation :

    ```plaintext
    @workspace #editor Describe the ConsoleApp class
    ```

1. Prenez quelques minutes pour passer en revue la réponse.

    Vous devez voir une réponse similaire à la description suivante :

    ```markdown
    The ConsoleApp class in ConsoleApp.cs is responsible for managing the console-based user interface of the library management system. It handles user interactions, processes user inputs, and coordinates actions with the underlying services and repositories.

    ### Fields
    - _currentState: Tracks the current state of the console application.
    - matchingPatrons: A list of patrons that match a search query.
    - selectedPatronDetails: Holds details of the currently selected patron.
    - selectedLoanDetails: Holds details of the currently selected loan.
    - _patronRepository: An instance of IPatronRepository for accessing patron data.
    - _loanRepository: An instance of ILoanRepository for accessing loan data.
    - _loanService: An instance of ILoanService for performing loan-related operations.
    - _patronService: An instance of IPatronService for performing patron-related operations.

    ### Constructor
    - ConsoleApp(ILoanService loanService, IPatronService patronService, IPatronRepository patronRepository, ILoanRepository loanRepository): Initializes the ConsoleApp with the provided services and repositories.

    ### Methods
    - Run(): The main entry point for running the console application.
    - PatronSearch(): Handles the logic for searching patrons.
    - ReadPatronName(): Reads the patron's name from the console input.
    - PrintPatronsList(List<Patron> matchingPatrons): Prints a list of matching patrons to the console.
    - PatronSearchResults(): Handles the logic for displaying and selecting from the search results.
    - ReadInputOptions(CommonActions options, out int optionNumber): Reads input options from the console.
    - WriteInputOptions(CommonActions options): Writes the available input options to the console.
    - PatronDetails(): Displays details of the selected patron.
    - LoanDetails(): Displays details of the selected loan and handles actions like extending or returning the loan.

    The class uses a state machine approach to manage different states of the console application, such as searching for patrons, displaying search results, showing patron details, and handling loan details.
    ```

1. Ouvrez le fichier **Program.cs**.

1. Dans la vue Conversation, entrez un prompt qui génère une description du fichier Program.cs.

    Par exemple, entrez le prompt suivant dans la vue Conversation :

    ```plaintext
    @workspace #editor Describe the Program.cs file
    ```

1. Prenez quelques minutes pour passer en revue la réponse.

    Vous devez voir une réponse similaire à la description suivante :

    ```markdown
    The Program.cs file is the entry point for the console application. It sets up the dependency injection container, configures services, and starts the ConsoleApp.
    
    1. **Dependency Injection Setup**:
        - Creates a ServiceCollection to register services.
        - Builds a configuration object from the appSettings.json file.
        - Registers various services and repositories with different lifetimes (singleton, scoped).
    
    2. **Service Registration**:
        - Registers the repositories: JsonPatronRepository and JsonLoanRepository.
        - Registers the services: LoanService and PatronService.
        - Registers the JsonData class as a singleton.
        - Registers the ConsoleApp class as a singleton.
    
    3. **Service Provider**:
        - Builds the service provider from the registered services.
        - Retrieves the ConsoleApp service and runs it asynchronously.

    This setup ensures that all dependencies are properly injected and configured before the application starts running.
    ```

1. Développez le projet Library.Infrastructure, puis développez le dossier Data.

1. Ajoutez les fichiers **JsonData.cs**, **JsonLoanRepository.cs** et **JsonPatronRepository.cs** au contexte Conversation.

    Vous pouvez utiliser une opération de glisser-déplacer pour ajouter les fichiers de l’Explorateur de solutions à la vue Conversation. Vous pouvez également utiliser le bouton **Attach context** (trombone) dans la vue Conversation pour ajouter des fichiers au contexte Conversation.

1. Dans la vue Conversation, entrez un prompt qui génère une explication des classes d’accès aux données.

    Par exemple, entrez le prompt suivant dans la vue Conversation :

    ```plaintext
    @workspace /explain Explain how the data access classes work
    ```

1. Prenez quelques minutes pour passer en revue la réponse.

    Vous devez voir une réponse similaire à la description suivante :

    ```markdown
    The data access classes in this project are designed to handle the loading, saving, and manipulation of data stored in JSON files. These classes include JsonData, JsonPatronRepository, and JsonLoanRepository. Here's an explanation of how each class works:
    
    ### JsonData Class
    The JsonData class is responsible for loading and saving data from and to JSON files. It also provides methods to populate related entities.
    
    #### Key Responsibilities:
    1. **Loading Data**: The LoadData method loads data from JSON files into in-memory collections (Authors, Books, BookItems, Patrons, Loans).
    2. **Saving Data**: The SaveJson method saves data to JSON files. Specific methods like SaveLoans and SavePatrons handle saving loans and patrons, respectively.
    3. **Ensuring Data is Loaded**: The EnsureDataLoaded method ensures that data is loaded into memory before any operations are performed.
    4. **Populating Related Entities**: Methods like GetPopulatedPatron, GetPopulatedLoan, GetPopulatedBookItem, and GetPopulatedBook populate related entities to provide a complete view of the data.
    
    #### Example Methods:
    - **LoadData**: Loads all data from JSON files.
    - **SaveLoans**: Saves loan data to the JSON file.
    - **GetPopulatedPatron**: Populates a patron with related loans.
    - **SearchBookByTitle**: Searches for a book by its title.
    
    ### JsonPatronRepository Class
    The JsonPatronRepository class implements the IPatronRepository interface and provides methods to interact with patron data.

    #### Key Responsibilities:
    1. **Searching Patrons**: The SearchPatrons method searches for patrons by name. 
    2. **Getting a Patron**: The GetPatron method retrieves a patron by ID and populates related data.
    3. **Updating a Patron**: The UpdatePatron method updates patron information and saves it to the JSON file.
    
    #### Example Methods:
    - **SearchPatrons**: Searches for patrons whose names contain the search input.
    - **GetPatron**: Retrieves a patron by ID and populates related loans.
    - **UpdatePatron**: Updates patron information and saves it to the JSON file.
    
    ### JsonLoanRepository Class
    The JsonLoanRepository class implements the ILoanRepository interface and provides methods to interact with loan data.
    
    #### Key Responsibilities:
    1. **Getting a Loan**: The GetLoan method retrieves a loan by ID and populates related data.
    2. **Updating a Loan**: The UpdateLoan method updates loan information and saves it to the JSON file.
    
    #### Example Methods:
    - **GetLoan**: Retrieves a loan by ID and populates related book items and patrons.
    - **UpdateLoan**: Updates loan information and saves it to the JSON file.
    
    ### How They Work Together
    1. **Loading Data**: When the application starts, the JsonData class loads data from JSON files into memory.
    2. **Searching and Retrieving Data**: The JsonPatronRepository and JsonLoanRepository classes use the JsonData class to search and retrieve data. They ensure data is loaded before performing operations.
    3. **Updating Data**: When data is updated, the repository classes call methods on the JsonData class to save the updated data back to the JSON files.
    4. **Populating Related Entities**: The JsonData class provides methods to populate related entities, ensuring that when a patron or loan is retrieved, it includes related data like loans or book items.
    
    ### Example Workflow
    1. **Search for a Patron**:
        - The SearchPatrons method in JsonPatronRepository calls EnsureDataLoaded to ensure data is loaded.
        - It then searches the Patrons collection for matching names and returns the results.

    2. **Get a Loan**:
       - The GetLoan method in JsonLoanRepository calls EnsureDataLoaded to ensure data is loaded.
       - It retrieves the loan by ID and uses GetPopulatedLoan to include related book items and patrons.

    3. **Update a Patron**:
       - The UpdatePatron method in JsonPatronRepository calls EnsureDataLoaded to ensure data is loaded.
       - It updates the patron information and calls SavePatrons to save the updated data to the JSON file.

    By using these data access classes, the application can efficiently manage data stored in JSON files, ensuring that data is loaded, manipulated, and saved correctly.
    ```

1. Prenez quelques minutes pour examiner les fichiers de données JSON utilisés pour simuler des enregistrements de bibliothèque.

    Les fichiers de données JSON se trouvent dans le dossier src/Library.Console/Json.

    Les fichiers de données utilisent des propriétés d’ID pour lier des entités. Par exemple, un objet Loan a une propriété PatronId qui établit une liaison à un objet Patron avec le même ID. Les fichiers JSON contiennent des données pour les auteurs, les livres, les articles de livres, les usagers et les prêts.

    > [!NOTE]
    > Notez que les noms des auteurs, les titres des livres et les noms des usagers ont été anonymisés pour les besoins de ce projet guidé.

#### Tâche 3 : générer et exécuter l’application

L’exécution de l’application vous aidera à comprendre l’interface utilisateur, les fonctionnalités clés de l’application et l’interaction entre les composants d’application.

Utilisez les étapes suivantes pour terminer cette section de l’exercice :

1. Vérifiez que la vue **Explorateur de solutions** est ouverte.

    La vue Explorateur de solutions n’est pas la même que la vue Explorateur. La vue Explorateur de solutions utilise des fichiers projet et solution en tant que nœuds de « répertoire » pour afficher la structure de la solution.

1. Pour exécuter l’application, cliquez avec le bouton droit sur **Library.Console**, sélectionnez **Déboguer**, puis **Démarrer une nouvelle instance**.

    Si les options **Déboguer** et **Démarrer une nouvelle instance** ne sont pas visibles, vérifiez que vous utilisez la vue Explorateur de solutions et non la vue Explorateur.

    Les étapes suivantes vous guident à parcourir un cas d’usage simple.

1. Lorsque vous êtes invité à entrer un nom d’usager, tapez **One**, puis appuyez sur Entrée.

    > [!NOTE]
    > L’application utilise un processus de recherche qui respecte la casse. Vous devez entrer « One » avec une majuscule, « O ».

    Vous devez voir une liste d’usagers qui correspondent à la requête de recherche.

1. À l’invite « Input Options », tapez **2**, puis appuyez sur Entrée.

    Taper **2** permet de sélectionner le deuxième usager de la liste.

    Vous devriez voir le nom de l’usager et l’état de son abonnement, suivi des détails relatifs aux prêts de livres.

1. À l’invite « Input Options », tapez **1**, puis appuyez sur Entrée.

    Taper **1** permet de sélectionner le premier livre de la liste.

    Les détails du livre doivent s’afficher, y compris la date de retour maximale et l’état de retour.

1. À l’invite « Input Options », tapez **r**, puis appuyez sur Entrée.

    Taper **r** a comme conséquence de retourner le livre.

1. Vérifiez que le message « Book was successfully returned. » est affichée.

    Le message « Book was successfully returned. » doit être suivi des détails du livre. Les livres retournés sont marqués par **Returned: True**.

1. Pour commencer une nouvelle recherche, tapez **s**, puis appuyez sur Entrée.

1. Lorsque vous êtes invité à entrer un nom d’usager, tapez **One**, puis appuyez sur Entrée.

1. À l’invite « Input Options », tapez **2**, puis appuyez sur Entrée.

1. Vérifiez que le premier prêt de livre est marqué **Returned: True**.

1. À l’invite « Input Options », tapez **q**, puis appuyez sur Entrée.

1. Arrêtez la session de débogage.

#### Résumé - Exercice 2

Cet exercice vous a permis de comprendre le codebase de l’application de bibliothèque et la façon dont l’application interagit avec l’utilisateur. Vous avez utilisé GitHub Copilot pour générer des explications sur la structure du projet, les fichiers sélectionnés et les classes d’accès aux données. Vous avez également exécuté l’application pour voir comment fonctionne l’interface de la console et comment les composants de l’application interagissent.

### Exercice 3 : créer le référentiel GitHub et le fichier README vide

La création du dépôt GitHub pour votre code vous permet de partager votre travail avec d’autres personnes et de collaborer sur le projet.

#### Tâche 1 : créer un référentiel GitHub

Utilisez les étapes suivantes pour terminer cette section de l’exercice :

1. Vérifiez que votre compte GitHub est ouvert dans une fenêtre de navigateur.

    Si nécessaire, ouvrez une fenêtre de navigateur et utilisez les informations suivantes pour vous connecter :

    URL : `https://github.com/enterprises/Microsoft-APL/sso`

    E-mail/Nom d’utilisateur :`@lab.CloudPortalCredential(1).Username`

    Mot de passe : `@lab.CloudPortalCredential(1).Password`

1. Ouvrez le menu de votre compte GitHub, puis sélectionnez **Vos dépôts**.

    Vous devez voir un message indiquant que vous n’avez pas encore de référentiels.

1. Pour construire des commandes de configuration Git qui utilisent les informations d’identification de votre compte GitHub, ouvrez **Notepad**, puis générez les commandes Git suivantes :

    ```bash
    git config --global user.email "lab assigned email"
    git config --global user.name "user name"
    ```

    Remplacez **« lab assigned email »** par l’e-mail défini dans l’environnement de labo : `@lab.CloudPortalCredential(1).Username`

    Remplacez **« username »** par votre nom d’utilisateur.

1. Passez à la fenêtre Visual Studio Code.

1. Ouvrez le terminal intégré de Visual Studio Code.

    Dans le menu Terminal, sélectionnez **Nouveau terminal**.

1. Pour configurer Git à l’aide des informations d’identification associées à votre compte GitHub, entrez les deux commandes que vous avez construites dans Notepad.

1. Dans Visual Studio Code, ouvrez la vue Contrôle de code source.

1. Sélectionnez **Publier sur GitHub**.

    Si une boîte de dialogue s’ouvre et vous invite à vous connecter à l’aide de votre compte GitHub, procédez comme suit :

    1. Sélectionnez **Autoriser**.
    1. Sélectionnez le compte que vous utilisez pour cet environnement de labo.
    1. Si nécessaire, sélectionnez à nouveau **Publier sur GitHub**.

1. Acceptez le nom par défaut du référentiel (AccelerateDevGitHubCopilot) et sélectionnez **Publier dans un référentiel privé GitHub**.

    Notez que Visual Studio Code affiche des messages d’état pendant le processus de publication.

    Vous serez peut-être invité à autoriser à nouveau votre compte GitHub. Si c’est le cas, suivez les instructions à l’écran pour autoriser votre compte dans le navigateur. Cela peut entraîner la publication de votre référentiel avec le message « first commit ».

1. Si le code n’a pas été publié dans le référentiel et que vous ne revenez pas à la vue Contrôle de code source, entrez un message de commit, puis sélectionnez **Publier la branche**.

    Une fois le processus de publication terminé, un message vous informe que votre code a été correctement publié dans le dépôt GitHub que vous avez spécifié.

#### Tâche 2 : créer un fichier README vide dans GitHub

Utilisez les étapes suivantes pour terminer cette section de l’exercice :

1. Basculez vers la fenêtre du navigateur affichant votre compte GitHub.

1. Ouvrez le nouveau dépôt AccelerateDevGitHubCopilot dans votre compte GitHub.

    Si vous ne voyez pas votre dépôt AccelerateDevGitHubCopilot, actualisez la page. Si vous ne voyez toujours pas le dépôt, essayez d’effectuer les étapes suivantes :

    1. Basculez vers Visual Studio Code.
    1. Ouvrez vos notifications (une notification a été générée lors de la publication du nouveau dépôt).
    1. Sélectionnez **Ouvrir sur GitHub** pour ouvrir votre dépôt.

1. Sous l’onglet Code de votre dépôt AccelerateDevGitHubCopilot, sélectionnez **Ajouter un fichier README**.

1. Dans l’éditeur README.md, tapez **Bientôt disponible** , puis sélectionnez **Commiter les modifications**.

1. Dans la boîte de dialogue Commiter les modifications, sélectionnez **Commiter les modifications**.

#### Tâche 3 : tirer les modifications apportées à votre référentiel local

Utilisez les étapes suivantes pour terminer cette section de l’exercice :

1. Basculez vers Visual Studio Code et vérifiez que la vue Contrôle de code source est ouverte.

1. Ouvrez le menu **Autres actions**, puis sélectionnez **Tirer**.

    Le menu Autres actions peut être ouvert à l’aide des points de suspension dans le coin supérieur droit de la vue Contrôle de code source.

1. Ouvrez la vue EXPLORATEUR (réduisez l’EXPLORATEUR DE SOLUTIONS et utilisez l’explorateur de fichiers/dossiers par défaut de Visual Studio Code), puis développez le dossier **AccelerateDevGitHubCopilot**.

1. Ouvrez le fichier README.md.

    Vous devriez voir le message « Bientôt disponible ».

    > [!NOTE]
    > Vous pourriez avoir créé le contenu du fichier README directement dans Visual Studio Code, puis envoyé les mises à jour au référentiel GitHub.

Vous utiliserez GitHub Copilot Chat pour mettre à jour le fichier README de votre référentiel dans le prochain exercice.

#### Résumé - Exercice 3

Cet exercice vous a permis de créer un référentiel GitHub pour l’application de bibliothèque et un fichier README vide. Vous avez également extrait les modifications vers votre référentiel local pour vous assurer que vous disposez des dernières mises à jour.

### Exercice 4 : créer la documentation du projet pour le fichier README

Le fichier README est une partie essentielle de tout dépôt GitHub. Le README fournit des informations basées sur les besoins du projet, des contributeurs au projet et des parties prenantes.

Pour cet exercice de projet guidé, votre fichier README doit inclure les sections suivantes :

- **Titre du projet** : Un bref titre clair pour le projet.
- **Description** : Une explication détaillée du projet est et de ce à quoi il sert.
- **Structure du projet** : décomposition de la structure du projet, y compris les dossiers et fichiers clés.
- **Classes et interfaces clés** : liste des classes et interfaces clés dans le projet.
- **Utilisation** : Instructions sur l’utilisation du projet, avec des exemples fréquents de code.
- **Licence** : La licence sous laquelle se trouve le projet.

#### Tâche 1 : utiliser GitHub Copilot pour générer une documentation de projet

Dans cette section de l’exercice, vous allez utiliser GitHub Copilot pour créer la documentation du projet, et l’ajouter à votre fichier README.md.

Utilisez les étapes suivantes pour terminer cette section de l’exercice :

1. Ouvrez la vue Conversation.

    Lorsque vous êtes intéressé par du code ou des fichiers spécifiques, vous pouvez utiliser des opérations de glisser-déplacer pour ajouter des fichiers au contexte de la vue Conversation. Dans ce cas, vous êtes intéressé par la solution globale. Vous allez donc utiliser le participant `@workspace` plutôt que d’ajouter des fichiers individuels.

1. Pour générer la documentation du projet pour votre fichier README, entrez le prompt suivant :

    ```plaintext
    @workspace Generate the contents of a README.md file for the code repository. Use "Library App" as the project title. The README file should include the following sections: Description, Project Structure, Key Classes and Interfaces, Usage, License. Format all sections as raw markdown. Use a bullet list with indents to represent the project structure. Do not include ".gitignore" or the ".github", "bin", and "obj" folders.
    ```

    > [!NOTE]
    > L’utilisation de plusieurs prompts, un pour chaque section du fichier README, produirait des résultats plus détaillés. Un seul prompt est utilisé dans cet exercice afin de simplifier le processus.

1. Passez en revue la réponse pour vous assurer que chaque section est mise en forme comme Markdown.

    > [!NOTE]
    > Vous pouvez mettre à jour des sections du README individuellement afin de fournir des informations plus détaillées ou si elles ne sont pas correctement mises en forme. Vous pouvez également copier la réponse de GitHub Copilot dans le fichier README, puis apporter des corrections directement dans le fichier Markdown.

1. Avec le fichier Markdown ouvert dans l’éditeur, ouvrez le menu d’état de GitHub Copilot, puis sélectionnez **Enable completions for markdown**.

1. Copiez les sections de documentation suggérées dans le fichier README.md.

    GitHub Copilot peut générer des suggestions pour la documentation Markdown. Cette fonctionnalité peut vous aider à composer et mettre en forme des fichiers Markdown.

    Par exemple, vous pouvez sélectionner le contenu du fichier README.md, ouvrir la conversation inline, puis demander à GitHub Copilot de corriger la mise en forme de la documentation Markdown (« correct the formatting of the markdown documentation »).

1. Ajustez la mise en forme si nécessaire, puis enregistrez le fichier README.md mis à jour.

    Vous devez disposer d’un fichier README qui inclut le titre du projet, la description, la structure du projet, les interfaces et les classes clés, les instructions d’utilisation et les informations de licence.

    ```markdown
    # Library App
    
    ## Description
    Library App is a console-based application for managing library operations such as patron management, book loans, and membership renewals. It uses a JSON-based data storage system and provides various services to handle library functionalities.
    
    ## Project Structure
    - AccelerateDevGitHubCopilot.sln
    - README.md
    - src
      - Library.ApplicationCore/
        - Entities/
          - `Author.cs`
          - `Book.cs`
          - `BookItem.cs`
          - `Loan.cs`
          - `Patron.cs`
        - Enums/
          - `LoanExtensionStatus.cs`
          - `LoanReturnStatus.cs`
          - `MembershipRenewalStatus.cs`
        - Interfaces/
          - `IPatronRepository.cs`
          - `IPatronService.cs`
          - `ILoanRepository.cs`
          - `ILoanService.cs`
        - `Library.ApplicationCore.csproj`
        - Services/
          - `PatronService.cs`
          - `LoanService.cs`
      - Library.Console/
        - `appSettings.json`
        - `CommonActions.cs`
        - `ConsoleApp.cs`
        - `ConsoleState.cs`
        - `Library.Console.csproj`
        - `Program.cs`
      - Library.Infrastructure/
        - Data/
          - `JsonData.cs`
          - `JsonLoanRepository.cs`
          - `JsonPatronRepository.cs`
        - `Library.Infrastructure.csproj`
    - tests
      - UnitTests/
        - ApplicationCore/
          - LoanService/
            - `ReturnLoan.cs`
            - `ExtendLoan.cs`
          - PatronService/
            - `RenewMembership.cs`
        - `UnitTests.csproj`
    
    ## Key Classes and Interfaces
    - **Entities**
      - **Author**: Represents an author with properties like Id and Name.
      - **Book**: Represents a book with properties like Id, Title, AuthorId, Genre, ImageName, and ISBN.
      - **BookItem**: Represents a specific copy of a book with properties like Id, BookId, AcquisitionDate, and Condition.
      - **Loan**: Represents a loan with properties like Id, BookItemId, PatronId, LoanDate, DueDate, and ReturnDate.
      - **Patron**: Represents a library patron with properties like Id, Name, MembershipStart, MembershipEnd, and Loans.
    
    - **Enums**
      - **LoanExtensionStatus**: Enum for loan extension statuses.
      - **LoanReturnStatus**: Enum for loan return statuses.
      - **MembershipRenewalStatus**: Enum for membership renewal statuses.
    
    - **Interfaces**
      - **IPatronRepository**: Interface for patron repository with methods like GetPatron, SearchPatrons, and UpdatePatron.
      - **IPatronService**: Interface for patron service with method RenewMembership.
      - **ILoanRepository**: Interface for loan repository with methods like GetLoan and UpdateLoan.
      - **ILoanService**: Interface for loan service with methods like ReturnLoan and ExtendLoan.
    
    - **Services**
      - **PatronService**: Implements IPatronService to handle patron-related operations.
      - **LoanService**: Implements ILoanService to handle loan-related operations.
    
    - **Console**
      - **ConsoleApp**: Main console application class that handles user interactions and application flow.
      - **ConsoleState**: Enum for different states of the console application.
      - **CommonActions**: Enum for common actions in the console application.
    
    - **Infrastructure**
      - **JsonData**: Handles loading and saving data to JSON files.
      - **JsonLoanRepository**: Implements ILoanRepository to manage loan data.
      - **JsonPatronRepository**: Implements IPatronRepository to manage patron data.
    
    ## Usage
    1. Clone the repository.
    2. Open the solution file AccelerateDevGitHubCopilot.sln in Visual Studio.
    3. Build the solution to restore dependencies.
    4. Run the Library.Console project to start the console application.
    5. Follow the on-screen instructions to search for patrons, view patron details, extend loans, return books, and renew memberships.
    
    ## License
    This project is licensed under the MIT License.
    ```

#### Tâche 2 : commiter et envoyer (push) les mises à jour du fichier README

Utilisez les étapes suivantes pour terminer cette section de l’exercice :

1. Ouvrez la vue Contrôle de code source de Visual Studio Code.

1. Pour que GitHub Copilot génère un message de commit, sélectionnez l’icône située à droite de la zone de message.

    Vous devez recevoir un message de commit similaire au suivant :

    ```plaintext
    Update README.md with project description, structure, key classes, usage instructions, and license information
    ```

1. Indexez et commitez les mises à jour de fichier.

1. Synchronisez (ou envoyez (push)) vos mises à jour vers le dépôt GitHub.

    Autorisez l’opération de synchronisation/push à l’aide de vos informations d’identification GitHub si vous y êtes invité.

#### Tâche 3 : vérifier votre travail

Pour vérifier votre travail, effectuez ces étapes :

1. Ouvrez le dépôt GitHub pour le projet AccelerateDevGitHubCopilot.

1. Utilisez l’onglet **Code** pour passer en revue le fichier README.md mis à jour.

    Il se peut que vous deviez actualiser votre navigateur pour voir le fichier README mis à jour.

1. Vérifiez que la structure du projet décrite dans le fichier README correspond à la structure de dossiers du dépôt.

    Lors de l’aperçu du fichier README, vous pouvez utiliser l’arborescence de fichiers sur le côté gauche de l’interface GitHub pour développer et examiner la structure du référentiel.

1. Passez en revue l’historique des commits et recherchez le message de commit généré par GitHub Copilot.

#### Résumé - Exercice 4

Cet exercice vous a aidé à créer la documentation du projet pour le fichier README à l’aide de GitHub Copilot. Vous avez utilisé GitHub Copilot pour générer la description du projet, la structure du projet, les interfaces et les classes clés, les instructions d’utilisation et les informations de licence. Vous avez également commité et envoyé (push) les mises à jour du fichier README vers le référentiel GitHub.

## Partie 2 : développer des fonctionnalités de code à l’aide des outils GitHub Copilot

### Avant de commencer

#### Vue d'ensemble du projet

Vous rencontrez votre collègue afin de discuter de vos objectifs pour l’application de bibliothèque. Vous souhaitez améliorer l’expérience utilisateur pour les bibliothécaires et les usagers. Vous discutez de plusieurs nouvelles fonctionnalités qui pourraient être ajoutées à l’application.

Vous acceptez de travailler sur les fonctionnalités suivantes :

- Disponibilité des livres : permettre à un bibliothécaire de déterminer l’état de disponibilité d’un livre. Cette fonctionnalité doit afficher un message indiquant si un livre est disponible pour le prêt, ou la date d’échéance du retour si le livre est actuellement prêté à un autre usager.

- Prêts de livres : permettre à un bibliothécaire de prêter un livre à un usager (si le livre est disponible). Cette fonctionnalité doit afficher l’option permettant de prêter un livre à un usager, de mettre à jour Loans.json avec le nouveau prêt, et d’afficher les détails du prêt mis à jour pour l’usager.

- Réservations de livres : permettre à un bibliothécaire de réserver un livre pour un usager (sauf si le livre est déjà réservé). Cette fonctionnalité doit implémenter un nouveau processus de réservation de livre. Cette fonctionnalité peut nécessiter la création d’un fichier Reservations.json, ainsi que des nouvelles classes et interfaces requises pour prendre en charge le processus de réservation.

Chacun d’entre vous travaillera sur l’une des nouvelles fonctionnalités, puis vous les regrouperez. Vous allez travailler sur la fonctionnalité permettant de déterminer l’état de disponibilité d’un livre. Votre collègue travaillera sur la fonctionnalité de prêt d’un livre à un usager. La dernière fonctionnalité, permettant de réserver un livre pour un usager, sera développée une fois les deux autres fonctionnalités terminées.

#### Scénario de labo (partie 2)

GitHub Copilot peut vous aider à développer de nouvelles fonctionnalités pour l’application de bibliothèque.

Dans la partie 2 de ce labo, vous allez utiliser GitHub Copilot pour générer des suggestions de code qui vous aideront à implémenter les nouvelles fonctionnalités plus rapidement et plus précisément.

La partie 2 comprend les exercices suivants :

- Développer une nouvelle fonctionnalité « disponibilité des livres ».
- Fusionner vos modifications dans la branche primaire du référentiel.

### Exercice 5 : développer une nouvelle fonctionnalité « disponibilité des livres »

La fonctionnalité de disponibilité de livre doit inclure les mises à jour de code suivantes :

- Implémenter une nouvelle action CommonActions.SearchBooks qui permet à un bibliothécaire de sélectionner l’option de recherche de livre.
- Créer une méthode SearchBooks dans ConsoleApp.cs. La méthode SearchBooks doit lire un titre de livre fourni par l’utilisateur. Vérifier si un livre est disponible pour le prêt, et afficher un message indiquant « book.title is available for loan » ou « book.title is on loan to another patron. The return due date is loan.DueDate.

Au cours de cet exercice, vous allez effectuer les tâches suivantes :

- Créer une branche « disponibilité des livres » dans le référentiel de code.
- Utilisez des suggestions GitHub Copilot pour vous aider à implémenter une nouvelle action courante SearchBooks qui pourra être sélectionnée par un bibliothécaire.
- Utilisez des suggestions GitHub Copilot pour vous aider à développer la méthode SearchBooks qui lit un titre de livre fourni par l’utilisateur, vérifie si un livre est disponible pour le prêt et affiche un message indiquant l’état de disponibilité du livre.

#### Tâche 1 : créer une branche dans le référentiel

Avant de commencer à développer la nouvelle fonctionnalité « disponibilité des livres », vous devez créer une branche dans le dépôt. Cela vous permet de travailler sur la nouvelle fonctionnalité sans affecter la branche principale du dépôt. Vous pourrez fusionner la nouvelle fonctionnalité dans la branche principale quand elle sera prête.

Utilisez les étapes suivantes pour terminer cette section de l’exercice :

1. Vérifiez que la solution AccelerateDevGitHubCopilot est ouverte dans Visual Studio Code.

1. Sélectionnez la vue Contrôle de code source et vérifiez que le dépôt local est synchronisé avec le dépôt distant (effectuez une demande de tirage ou une synchronisation).

1. Dans l’angle inférieur gauche de la fenêtre, sélectionnez **main**.

1. Pour créer une branche, tapez **disponibilité des livres**, puis sélectionnez **+ Créer une branche**.

1. Pour envoyer (push) la nouvelle branche vers le dépôt distant, sélectionnez **Publier la branche**.

#### Tâche 2 : implémenter une nouvelle action courante « SearchBooks »

Dans cette section de l’exercice, vous utilisez GitHub Copilot pour vous aider à implémenter une option de menu nommée SearchBooks. Les bibliothécaires choisiront l’action SearchBooks pour vérifier l’état de disponibilité d’un livre.

Voici les mises à jour de fichier que vous effectuez pendant cette tâche :

- Mettez à jour l’énumération CommonActions dans CommonActions.cs : ajoutez une nouvelle action SearchBooks à l’énumération CommonActions.
- Mettez à jour la méthode WriteInputOptions dans ConsoleApp.cs : ajoutez la prise en charge de l’affichage de la nouvelle option CommonActions.SearchBooks.
- Mettez à jour la méthode ReadInputOptions dans ConsoleApp.cs : ajoutez la prise en charge de la lecture (sélection) de la nouvelle option CommonActions.SearchBooks.
- Mettez à jour la méthode PatronDetails dans ConsoleApp.cs : ajoutez la prise en charge du traitement de la nouvelle option CommonActions.SearchBooks lorsqu’elle est sélectionnée.

Utilisez les étapes suivantes pour terminer cette section de l’exercice :

1. Ouvrez la vue EXPLORATEUR DE SOLUTIONS.

1. Ouvrez le fichier CommonActions.cs, puis sélectionnez l’énumération **CommonActions**.

    Vous devez ajouter une nouvelle action SearchBooks à CommonActions.

1. Ouvrez la conversation en ligne, puis entrez le prompt suivant :

    ```plaintext
    Update selection to include a new `SearchBooks` action.
    ```

    GitHub Copilot doit suggérer une mise à jour de code qui ajoute la nouvelle action SearchBooks à l’énumération CommonActions.

1. Passez en revue la mise à jour suggérée, puis sélectionnez **Accepter**.

    ```csharp

    public enum CommonActions
    {
        Repeat = 0,
        Select = 1,
        Quit = 2,
        SearchPatrons = 4,
        RenewPatronMembership = 8,
        ReturnLoanedBook = 16,
        ExtendLoanedBook = 32,
        SearchBooks = 64
    }

    ```

1. Ouvrez le fichier ConsoleApp.cs.

1. Recherchez, puis sélectionnez la méthode **WriteInputOptions**.

    Vous devez ajouter la prise en charge de la nouvelle option CommonActions.SearchBooks. Affichez l’option permettant de vérifier si un livre est disponible pour le prêt.

1. Ouvrez la conversation en ligne, puis entrez le prompt suivant :

    ```plaintext
    Update selection to include an option for the `CommonActions.SearchBooks` action. Use the letter "b" and the message "to check for book availability".
    ```

    GitHub Copilot doit suggérer une mise à jour de code qui ajoute un nouveau bloc « if » pour l’action SearchBooks.

1. Passez en revue la mise à jour suggérée, puis sélectionnez **Accepter**.

    La mise à jour suggérée doit être similaire à l’extrait de code suivant :

    ```csharp

    static void WriteInputOptions(CommonActions options)
    {
        Console.WriteLine("Input Options:");
        if (options.HasFlag(CommonActions.ReturnLoanedBook))
        {
            Console.WriteLine(" - \"r\" to mark as returned");
        }
        if (options.HasFlag(CommonActions.ExtendLoanedBook))
        {
            Console.WriteLine(" - \"e\" to extend the book loan");
        }
        if (options.HasFlag(CommonActions.RenewPatronMembership))
        {
            Console.WriteLine(" - \"m\" to extend patron's membership");
        }
        if (options.HasFlag(CommonActions.SearchPatrons))
        {
            Console.WriteLine(" - \"s\" for new search");
        }
        if (options.HasFlag(CommonActions.SearchBooks))
        {
            Console.WriteLine(" - \"b\" to check for book availability");
        }
        if (options.HasFlag(CommonActions.Quit))
        {
            Console.WriteLine(" - \"q\" to quit");
        }
        if (options.HasFlag(CommonActions.Select))
        {
            Console.WriteLine("Or type a number to select a list item.");
        }
    }

    ```

1. Faites défiler un peu vers le haut pour trouver la méthode **ReadInputOptions**.

1. Sélectionnez la méthode **ReadInputOptions**.

    Vous devez ajouter la prise en charge de la nouvelle option CommonActions.SearchBooks. Incluez un cas qui gère la sélection de l’action SearchBooks par l’utilisateur.

1. Ouvrez la conversation en ligne, puis entrez le prompt suivant :

    ```plaintext
    Update selection to include an option for the `CommonActions.SearchBooks` action.
    ```

    GitHub Copilot doit suggérer une mise à jour de code qui ajoute un nouveau « case » qui gère la sélection de l’action SearchBooks par l’utilisateur.

1. Passez en revue la mise à jour suggérée, puis sélectionnez **Accepter**.

    La mise à jour suggérée doit être similaire à l’extrait de code suivant :

    ```csharp

    static CommonActions ReadInputOptions(CommonActions options, out int optionNumber)
    {
        CommonActions action;
        optionNumber = 0;
        do
        {
            Console.WriteLine();
            WriteInputOptions(options);
            string? userInput = Console.ReadLine();
            action = userInput switch
            {
                "q" when options.HasFlag(CommonActions.Quit) => CommonActions.Quit,
                "s" when options.HasFlag(CommonActions.SearchPatrons) => CommonActions.SearchPatrons,
                "m" when options.HasFlag(CommonActions.RenewPatronMembership) => CommonActions.RenewPatronMembership,
                "e" when options.HasFlag(CommonActions.ExtendLoanedBook) => CommonActions.ExtendLoanedBook,
                "r" when options.HasFlag(CommonActions.ReturnLoanedBook) => CommonActions.ReturnLoanedBook,
                "b" when options.HasFlag(CommonActions.SearchBooks) => CommonActions.SearchBooks,
                _ when int.TryParse(userInput, out optionNumber) => CommonActions.Select,
                _ => CommonActions.Repeat
            };
            if (action == CommonActions.Repeat)
            {
                Console.WriteLine("Invalid input. Please try again.");
            }
        } while (action == CommonActions.Repeat);
        return action;
    }

    ```

1. Faites défiler vers le bas pour rechercher et sélectionner la méthode **PatronDetails**.

    Vous devez effectuer deux opérations :

    - Vous devez ajouter CommonActions.SearchBooks aux options avant d’appeler ReadInputOptions.
    - Vous devez également ajouter un « else if » pour gérer l’action SearchBooks. Le bloc « else if » doit appeler une nouvelle méthode nommée SearchBooks.

    Vous pouvez traiter ces deux opérations en même temps.

1. Ouvrez la conversation en ligne, puis entrez le prompt suivant :

    ```plaintext
    Update selection to add `CommonActions.SearchBooks` to `options` before calling `ReadInputOptions`. Add an `else if` block to handle the `SearchBooks` action. The `else if` block should call a new method named `SearchBooks`.
    ```

    GitHub Copilot doit suggérer une mise à jour de code qui ajoute CommonActions.SearchBooks aux options avant d’appeler ReadInputOptions.

1. Passez en revue la mise à jour suggérée, puis sélectionnez **Accepter**.

    ```csharp

    async Task<ConsoleState> PatronDetails()
    {
        Console.WriteLine($"Name: {selectedPatronDetails.Name}");
        Console.WriteLine($"Membership Expiration: {selectedPatronDetails.MembershipEnd}");
        Console.WriteLine();
        Console.WriteLine("Book Loans:");
        int loanNumber = 1;
        foreach (Loan loan in selectedPatronDetails.Loans)
        {
            Console.WriteLine($"{loanNumber}) {loan.BookItem!.Book!.Title} - Due: {loan.DueDate} - Returned: {(loan.ReturnDate != null).ToString()}");
            loanNumber++;
        }
        CommonActions options = CommonActions.SearchPatrons | CommonActions.Quit | CommonActions.Select | CommonActions.RenewPatronMembership | CommonActions.SearchBooks;
        CommonActions action = ReadInputOptions(options, out int selectedLoanNumber);
        if (action == CommonActions.Select)
        {
            if (selectedLoanNumber >= 1 && selectedLoanNumber <= selectedPatronDetails.Loans.Count())
            {
                var selectedLoan = selectedPatronDetails.Loans.ElementAt(selectedLoanNumber - 1);
                selectedLoanDetails = selectedPatronDetails.Loans.Where(l => l.Id == selectedLoan.Id).Single();
                return ConsoleState.LoanDetails;
            }
            else
            {
                Console.WriteLine("Invalid book loan number. Please try again.");
                return ConsoleState.PatronDetails;
            }
        }
        else if (action == CommonActions.Quit)
        {
            return ConsoleState.Quit;
        }
        else if (action == CommonActions.SearchPatrons)
        {
            return ConsoleState.PatronSearch;
        }
        else if (action == CommonActions.RenewPatronMembership)
        {
            var status = await _patronService.RenewMembership(selectedPatronDetails.Id);
            Console.WriteLine(EnumHelper.GetDescription(status));
            // reloading after renewing membership
            selectedPatronDetails = (await _patronRepository.GetPatron(selectedPatronDetails.Id))!;
            return ConsoleState.PatronDetails;
        }
        else if (action == CommonActions.SearchBooks)
        {
            return await SearchBooks();
        }
        throw new InvalidOperationException("An input option is not handled.");
    }

    ```

    > [!NOTE]
    > Les suggestions de conversation en ligne peuvent également créer un stub de code pour la méthode SearchBooks.

#### Tâche 3 : développer la méthode SearchBooks

Une fois terminé, la méthode SearchBooks doit lire un titre de livre fourni par l’utilisateur, vérifier si un livre est disponible pour le prêt et afficher un message indiquant l’état de disponibilité du livre. La méthode doit utiliser les fichiers Books.json et Loans.json pour rechercher le titre du livre correspondant et déterminer l’état de disponibilité du livre.

Utilisez les étapes suivantes pour terminer cette section de l’exercice :

1. Consacrez une minute à l’évaluation des exigences de processus de la méthode SearchBooks.

    Que doit faire la méthode ? Que doit-elle retourner ? Nécessite-t-elle des paramètres ?

    La méthode SearchBooks doit implémenter le processus suivant :

    1. Inviter l’utilisateur à entrer un titre de livre.
    1. Lire le titre du livre fourni par l’utilisateur.
    1. Vérifier si un livre est disponible pour le prêt
    1. Afficher un message indiquant l’une des options suivantes :

        - « book.title is available for loan »
        - « book.title is on loan to another patron. The return due date is loan.DueDate.

    Pour générer les options de message, votre code doit accéder aux fichiers JSON suivants :

    - Books.json est nécessaire pour trouver les valeurs Title et BookId correspondantes.
    - Loans.json est nécessaire pour rechercher les valeurs ReturnDate et DueDate pour l’objet BookItemId correspondantes. La valeur BookItemId est la même que pour BookId dans Books.json.

1. Vérifiez que la méthode **SearchBooks** suivante a été créée dans le fichier ConsoleApp.cs :

    ```csharp

    async Task<ConsoleState> SearchBooks()
    {
        return ConsoleState.PatronDetails;
    }

    ```

    > [!NOTE]
    > N’oubliez pas de supprimer les commentaires de code créés par GitHub Copilot. Les commentaires inutiles et incorrects peuvent influencer négativement les suggestions de GitHub Copilot.

1. Sélectionnez la méthode **SearchBooks**.

1. Ouvrez la conversation en ligne, puis entrez le prompt suivant :

    ```plaintext
    Update selection to obtain a book title. Prompt the user to "Enter a book title to search for". Read the user input and ensure the book title isn't null.
    ```

    GitHub Copilot doit suggérer une mise à jour de code qui capture le titre du livre fourni par l’utilisateur.

1. Passez en revue la mise à jour suggérée, puis sélectionnez **Accepter**.

    ```csharp

    async Task<ConsoleState> SearchBooks()
    {
        string? bookTitle = null;
        while (String.IsNullOrWhiteSpace(bookTitle))
        {
            Console.Write("Enter a book title to search for: ");
            bookTitle = Console.ReadLine();
        }
        // Perform book search logic here
        return ConsoleState.PatronDetails;
    }

    ```

    > [!NOTE]
    > GitHub Copilot peut créer une méthode distincte pour gérer l’entrée par un utilisateur d’un titre de livre. Vous pouvez accepter cette suggestion et continuer à développer la logique principale dans la méthode SearchBooks.

1. Supprimez les commentaires d’espace réservé générés par GitHub Copilot, puis sélectionnez la méthode **SearchBooks**.

1. Ouvrez l’affichage Conversation.

1. Ajoutez les fichiers suivants au contexte Conversation : ConsoleApp.cs, JsonData.cs, JsonLoanRepository.cs, Books.json, Loans.json, BookItems.json.

1. Entrez l’invite suivante :

    ```plaintext
    @workspace  Explain how to update the `SearchBooks` method and ConsoleApps class to determine whether a book title is available for loan. Inside the SearchBooks method, use a LINQ query and the user supplied book title to return a matching book. If a book is found, use a LINQ query and Loans.json to check if the book is available for loan. If the book has been returned, display a message stating "`book.title` is available for loan". If the book is on loan, display a message stating "`book.title` is on loan to another patron. The return due date is `loan.DueDate`".
    ```

1. Prenez une minute pour passer en revue les mises à jour suggérées.

    GitHub Copilot doit proposer des mises à jour similaires aux suggestions suivantes :

    Pour mettre à jour la méthode SearchBooks et la classe ConsoleApp afin de déterminer si un titre de livre est disponible pour le prêt, procédez comme suit :

    a. Ajoutez une méthode pour rechercher des livres par titre dans la classe JsonData.
    b. Mettez à jour la méthode SearchBooks dans la classe ConsoleApp pour utiliser cette nouvelle méthode.
    c. Vérifiez l’état du prêt du livre et affichez le message approprié.

    Voici le code mis à jour :

    Étape 1 : ajouter une méthode pour rechercher des livres par titre dans la classe JsonData

    ```csharp

    public Book? SearchBookByTitle(string title)
    {
        return Books?.FirstOrDefault(b => b.Title.Equals(title, StringComparison.OrdinalIgnoreCase));
    }

    ```

    Étape 2 : mettre à jour la méthode SearchBooks dans la classe ConsoleApp

    ```csharp

    async Task<ConsoleState> SearchBooks()
    {
        string bookTitle = ReadBookTitle();
        // ensure data is loaded
        await _jsonData.LoadData();
        // find the book by title
        Book? book = _jsonData.SearchBookByTitle(bookTitle);
        if (book == null)
        {
            Console.WriteLine($"No book found with title: {bookTitle}");
            return ConsoleState.PatronDetails;
        }
        // find the loan status of the book
        Loan? loan = _jsonData.Loans?.FirstOrDefault(l => l.BookItemId == book.Id && l.ReturnDate == null);
        if (loan == null)
        {
            Console.WriteLine($"{book.Title} is available for loan.");
        }
        else
        {
            Console.WriteLine($"{book.Title} is on loan to another patron. The return due date is {loan.DueDate}.");
        }
        return ConsoleState.PatronDetails;
    }

    ```

    Étape 3 : mettre à jour le constructeur de classe ConsoleApp pour inclure JsonData

    ```csharp

    public class ConsoleApp
    {
        // Existing fields...
        JsonData _jsonData;
        public ConsoleApp(ILoanService loanService, IPatronService patronService, IPatronRepository patronRepository, ILoanRepository loanRepository, JsonData jsonData)
        {
            _patronRepository = patronRepository;
            _loanRepository = loanRepository;
            _loanService = loanService;
            _patronService = patronService;
            _jsonData = jsonData;
        }
        // Other methods...

    }

    ```

    Étape 4 : mettre à jour le Program.cs pour passer JsonData à ConsoleApp

    ```csharp

    using Microsoft.Extensions.DependencyInjection;
    using Library.Infrastructure.Data;
    using Library.ApplicationCore;
    using Microsoft.Extensions.Configuration;
    var services = new ServiceCollection();
    var configuration = new ConfigurationBuilder()
    .SetBasePath(Directory.GetCurrentDirectory())
    .AddJsonFile("appSettings.json")
    .Build();
    services.AddSingleton<IConfiguration>(configuration);
    services.AddScoped<IPatronRepository, JsonPatronRepository>();
    services.AddScoped<ILoanRepository, JsonLoanRepository>();
    services.AddScoped<ILoanService, LoanService>();
    services.AddScoped<IPatronService, PatronService>();
    services.AddSingleton<JsonData>();
    services.AddSingleton<ConsoleApp>();
    var servicesProvider = services.BuildServiceProvider();
    var consoleApp = servicesProvider.GetRequiredService<ConsoleApp>();
    consoleApp.Run().Wait();

    ```

    Avec ces modifications, la méthode SearchBooks de la classe ConsoleApp recherche désormais un livre par titre dans le fichier Books.json et vérifie son état de prêt dans le fichier Loans.json. Si le livre est disponible pour le prêt, elle affiche un message indiquant que le livre est disponible. Si le livre est déjà emprunté, elle affiche un message indiquant que le livre est en cours de prêt et indique la date d’échéance du retour.

    > [!NOTE]
    > GitHub Copilot peut suggérer d’utiliser des requêtes LINQ dans la méthode SearchBooks pour renvoyer un objet book plutôt que d’utiliser une méthode dans la classe JsonData. Toutefois, il peut également suggérer la création de méthodes dans la classe `JsonData` pour retourner un titre de livre et vérifier l’état du prêt (plutôt que d’utiliser des requêtes LINQ dans la méthode SearchBooks). Les instructions qui suivent sont basées sur des suggestions GitHub Copilot qui utilisent une combinaison de ces approches.

1. Ajoutez la méthode SearchBookByTitle suggérée à la fin de la classe **JsonData**.

    ```csharp

    public Book? SearchBookByTitle(string title)
    {
        return Books?.FirstOrDefault(b => b.Title.Equals(title, StringComparison.OrdinalIgnoreCase));
    }

    ```

1. Ajoutez la déclaration du champ _jsonData à la classe ConsoleApp avant le constructeur de classe.

    ```csharp

    JsonData _jsonData;

    ```

1. Ajoutez un paramètre jsonData au constructeur de classe ConsoleApp, et utilisez-le pour initialiser le champ _jsonData à l’intérieur du constructeur.

    Le constructeur de classe mis à jour doit ressembler à l’extrait de code suivant :

    ```csharp

    public ConsoleApp(ILoanService loanService, IPatronService patronService, IPatronRepository patronRepository, ILoanRepository loanRepository, JsonData jsonData)
    {
        _patronRepository = patronRepository;
        _loanRepository = loanRepository;
        _loanService = loanService;
        _patronService = patronService;
        _jsonData = jsonData;
    }

    ```

1. Notez que JsonData n’est pas reconnu dans la classe ConsoleApp.

    Vous devez ajouter « using Library.Infrastructure.Data » en haut du fichier ConsoleApp.cs.

1. Vérifiez que l’instruction « using » suivante est ajoutée en haut du fichier ConsoleApp.cs.

    ```csharp

    using Library.Infrastructure.Data;

    ```

1. Utilisez les suggestions de code pour mettre à jour la méthode **SearchBooks** :

    Le code suggéré doit utiliser la méthode SearchBookByTitle (ou une requête LINQ) pour rechercher le livre par titre. Si le livre est trouvé, une requête LINQ est utilisée pour déterminer si le livre est déjà emprunté. Le code inclut également la logique permettant d’afficher l’état de disponibilité du livre en fonction des résultats de la recherche. La logique utilisée pour afficher les messages de réponse peut être implémentée de plusieurs façons. Un exemple est fourni dans l’extrait de code ci-dessous.

    L’extrait de code suivant montre une implémentation possible de la méthode SearchBooks :

    ```csharp

    async Task<ConsoleState> SearchBooks()
    {
        string bookTitle = ReadBookTitle();
        Book? book = _jsonData.SearchBookByTitle(bookTitle);
        if (book == null)
        {
            Console.WriteLine($"No book found with title: {bookTitle}");
            return ConsoleState.PatronDetails;
        }
        Loan? loan = _jsonData.Loans?.FirstOrDefault(l => l.BookItemId == book.Id && l.ReturnDate == null);
        if (loan == null)
        {
            Console.WriteLine($"{book.Title} is available for loan.");
        }
        else
        {
            Console.WriteLine($"{book.Title} is on loan to another patron. The return due date is {loan.DueDate}.");
        }
        return ConsoleState.PatronDetails;
    }

    ```

1. Comparez le fichier **Program.cs** existant avec les mises à jour suggérées.

    ```csharp

    using Microsoft.Extensions.DependencyInjection;
    using Library.Infrastructure.Data;
    using Library.ApplicationCore;
    using Microsoft.Extensions.Configuration;
    var services = new ServiceCollection();
    var configuration = new ConfigurationBuilder()
        .SetBasePath(Directory.GetCurrentDirectory())
        .AddJsonFile("appSettings.json")
        .Build();
    services.AddSingleton<IConfiguration>(configuration);
    services.AddScoped<IPatronRepository, JsonPatronRepository>();
    services.AddScoped<ILoanRepository, JsonLoanRepository>();
    services.AddScoped<ILoanService, LoanService>();
    services.AddScoped<IPatronService, PatronService>();
    services.AddSingleton<JsonData>();
    services.AddSingleton<ConsoleApp>();
    var servicesProvider = services.BuildServiceProvider();
    var consoleApp = servicesProvider.GetRequiredService<ConsoleApp>();
    consoleApp.Run().Wait();

    ```

    Aucune mise à jour n’est requise si le fichier Program.cs inclut déjà le code qui indique au système d’injection de dépendances ASP.NET Core de créer une seule instance de la classe JsonData et d’utiliser cette même instance chaque fois qu’un JsonData est demandé.

1. Sélectionnez la méthode **SearchBooks**.

1. Ouvrez la vue Conversation, puis entrez l’invite suivante :

    ```plaintext
    Explain the LINQ queries and the evaluation of the book's availability status.
    ```

1. Prenez un moment pour examiner les explications fournies par GitHub Copilot.

    Pour la requête qui vérifie si le livre est emprunté, vous devez voir une description similaire à l’explication suivante :

    ```markdown
    **Search for the Loan Status of the Book**
    ```

    ```csharp

    Loan? loan = _jsonData.Loans?.FirstOrDefault(l => l.BookItemId == book.Id && l.ReturnDate == null);

    ```

    ```markdown
    - _jsonData.Loans: Accesses the list of loans from the JsonData class.

    - ?.: The null-conditional operator ensures that if _jsonData.Loans is null, the entire expression will return null without throwing a NullReferenceException.

    - FirstOrDefault: A LINQ method that returns the first element in the collection that matches the specified condition, or null if no such element is found.

    - Lambda Expression: l => l.BookItemId == book.Id && l.ReturnDate == null

        - l.BookItemId == book.Id: Checks if the BookItemId of the loan matches the Id of the book being searched.

        - l.ReturnDate == null: Checks if the loan's ReturnDate is null, indicating that the book is currently on loan and has not been returned.

    - Result: If a matching loan is found, it is assigned to the loan variable. If no matching loan is found, loan is null.

    **Evaluation of the Book's Availability Status**

    After executing the LINQ queries, the method evaluates the availability status of the book:

      - If loan is null, the book has been returned. The method prints that the book is available for loan.
      - If loan is not null, the book is currently on loan (no return date). The method prints that the book is on loan and provides the date when the book should be returned.

    ```

1. Vérifiez la logique implémentée par la requête **Check if the Book is on Loan**.

    Opérateur conditionnel Null : l’opérateur « ?. » est appelé opérateur conditionnel Null. Il garantit que si _jsonData.Loans est null, l’expression entière sera évaluée comme null sans lever de NullReferenceException.

    Expression lambda : l’expression lambda « l => l.BookItemId == book.Id && l.ReturnDate == null » définit la condition de la méthode FirstOrDefault. Elle vérifie chaque objet loan « I » pour voir si son BookItemId correspond à l’ID de l’objet book et si son ReturnDate est null.

    Ce code tente de trouver le premier prêt dans la collection _jsonData.Loans où le BookItemId correspond à l’ID du livre donné et où ReturnDate est null. Si aucun prêt correspondant n’est trouvé ou si « _jsonData.Loans » est null, le prêt est défini sur null.

    > [!NOTE]
    > La plupart des bibliothèques modernes ont plusieurs copies du même livre. Ce code part du principe qu’il n’y a qu’une seule copie de chaque livre. Si la bibliothèque a plusieurs copies du même livre, le code doit être mis à jour de façon à gérer plusieurs prêts pour le même livre. Dans le cadre de cette formation, nous partons du principe qu’il n’y a qu’une seule copie de chaque livre et que la logique fournie est suffisante.

1. Enregistrez vos fichiers de mise à jour.

1. Générez la solution pour vous assurer qu’elle ne contient aucune erreur.

    Vous verrez des messages d’**avertissement**, mais il ne doit y avoir aucune erreur.

    Pour générer la solution dans l’affichage Explorateur de solutions, cliquez avec le bouton droit sur **AccelerateDevGitHubCopilot**, puis sélectionnez **Générer**.

#### Résumé - Exercice 5

Vous avez utilisé GitHub Copilot pour vous aider à implémenter une nouvelle fonctionnalité pour l’application de bibliothèque. Vous avez créé une branche dans le référentiel, puis utilisé GitHub Copilot pour générer des suggestions de code qui vous ont aidé à implémenter la nouvelle fonctionnalité plus rapidement et plus précisément. Vous avez ajouté une nouvelle action SearchBooks à CommonActions, mis à jour les méthodes WriteInputOptions et ReadInputOptions dans ConsoleApp.cs, puis créé une nouvelle méthode SearchBooks pour déterminer l’état de disponibilité d’un livre.

### Exercice 6 : fusionner vos modifications dans la branche primaite du référentiel

Vous avez créé une nouvelle fonctionnalité qui permet à un bibliothécaire de déterminer l’état de disponibilité d’un livre. Vous devez maintenant vérifier que la fonctionnalité fonctionne comme prévu et fusionner vos modifications dans la branche primaire du référentiel.

Au cours de cet exercice, vous allez effectuer les tâches suivantes :

- Vérifier que votre nouvelle fonctionnalité fonctionne comme prévu
- Synchroniser vos modifications avec le dépôt distant
- Créer une demande de tirage (pull request) pour fusionner vos modifications dans la branche primaire du référentiel

#### Tâche 1 : vérifier que votre nouvelle fonctionnalité fonctionne comme prévu

Étant donné que vous n’avez pas de tests automatisés, vous pouvez utiliser des tests manuels pour vérifier que la nouvelle fonctionnalité fonctionne comme prévu. L’utilisation d’une source de données qui peut être vérifiée est important. Dans le cas présent, vous utilisez les fichiers Books.json et Loans.json pour vérifier que la nouvelle fonctionnalité signale correctement l’état de disponibilité d’un livre.

Utilisez les étapes suivantes pour terminer cette section de l’exercice :

1. Ouvrez la vue Explorateur de solutions.

1. Pour exécuter l’application, cliquez avec le bouton droit sur **Library.Console**, sélectionnez **Déboguer**, puis **Démarrer une nouvelle instance**.

1. Lorsque vous êtes invité à entrer un nom d’usager, tapez **One**, puis appuyez sur Entrée.

    Vous devez voir une liste d’usagers qui correspondent à la requête de recherche.

1. À l’invite « Input Options », tapez **2**, puis appuyez sur Entrée.

    Taper **2** permet de sélectionner le deuxième usager de la liste.

    Vous devriez voir le nom de l’usager et l’état de son abonnement, suivi des détails relatifs aux prêts de livres.

1. À l’invite « Input Options », tapez **b**, puis appuyez sur Entrée.

    Taper **b** permet de sélectionner l’option de recherche de l’état de disponibilité d’un livre.

    Vous devriez voir une invite pour entrer un titre de livre.

1. Tapez **Book One**, puis appuyez sur Entrée.

    Dans les données d’origine que vous avez téléchargées, **Book One** est actuellement prêté à **Patron Forty-Nine** ; il ne devrait donc pas être disponible.

1. Vérifiez que l’application affiche un message indiquant que le livre est actuellement prêté à un autre usager.

    Vous devrez peut-être faire défiler pour voir le message.

1. Vérifiez que **Book Nine** a été rendu par **Patron One**.

    Dans l’exercice précédent, lors d’un test de l’application de bibliothèque, vous aviez fait en sorte que **Patron One** rende **Book Nine**. Si l’application indique que **Book Nine** n’a pas été rendu par **Patron One**, utilisez les options d’entrée pour sélectionner et rendre **Book Nine** avant de continuer.

    > [!NOTE]
    > Le fichier Library.Console.csproj garantit que les fichiers de données JSON sont copiés dans le répertoire de sortie lorsque l’application est générée. Toutefois, l’exécution des opérations de nettoyage ou de reconstruction réinitialise les données. Les opérations de génération répétées ne réinitialisent pas les données dans le répertoire de sortie (« /bin/Debug/net8.0/ »).

1. À l’invite « Input Options », tapez **b**, puis appuyez sur Entrée.

1. Tapez **Book Nine**, puis appuyez sur Entrée.

1. Vérifiez que l’application affiche un message indiquant que le livre est disponible pour le prêt.

1. À l’invite « Input Options », tapez **q**, puis appuyez sur Entrée.

1. Arrêtez la session de débogage.

1. Ouvrez le fichier **Loans.json**.

    Le fichier Loans.json est utilisé pour suivre l’état du prêt de chaque livre. Vous pouvez utiliser le fichier Loans.json pour vérifier que l’état de disponibilité de Book One et Book Nine est correct.

    Le fichier Loans.json mis à jour doit se trouver dans le dossier « Library.Console\bin\Debug\net8.0\Json » ou dans le dossier « Library.Console\Json ».

    - Si vous utilisez le débogueur Visual Studio Code pour exécuter l’application, le fichier Loans.json mis à jour doit se trouver dans le dossier « Library.Console\bin\Debug\net8.0\Json ».

    - Si vous utilisez une commande « dotnet run » à partir du dossier « AccelerateDevGitHubCopilot\src\Library.Console » pour exécuter l’application, le fichier Loans.json mis à jour doit se trouver dans le dossier « Library.Console\Json ».

1. Vérifiez que l’ID de prêt 37 et l’ID de prêt 46 concernent tous les deux Book One (« BookItemId » : 1).

    - L’ID de prêt 37 doit avoir une valeur ReturnDate de (2024-01-17).
    - L’ID de prêt 46 ne doit pas avoir de valeur ReturnDate. La valeur ReturnDate doit être null.

    La valeur ReturnDate est utilisée pour déterminer si le livre est actuellement prêté. Si la valeur ReturnDate est null, le livre est considéré comme actuellement prêté.

1. Vérifiez que l’ID de prêt 22 concerne Book Nine (« BookItemId » : 9), et que la valeur ReturnDate est définie sur la date d’aujourd’hui.

    Si vous exécutez le débogueur et que vous avez nettoyé la solution après avoir apporté des modifications au fichier Loans.json, ces modifications sont perdues. Après le nettoyage de la solution, le fichier Loans.json est réinitialisé aux données d’origine lors de la prochaine exécution de l’application. Vous pouvez mettre à jour manuellement le fichier Loans.json afin de tester l’état de disponibilité de Book One et Book Nine.

#### Tâche 2 : synchroniser vos modifications avec le référentiel distant

Vous pouvez utiliser la vue Contrôle de code source dans Visual Studio Code pour commiter vos modifications dans le référentiel local. Une fois vos modifications commitées, vous pouvez les synchroniser avec le référentiel distant.

Utilisez les étapes suivantes pour terminer cette section de l’exercice :

1. Sélectionnez la vue Contrôle de code source.

1. Vérifiez que les fichiers CommonActions.cs, ConsoleApp.cs et JsonData.cs sont répertoriés sous **Modifications**.

    Si GitHub Copilot a utilisé des requêtes LINQ pour déterminer l’état de disponibilité d’un livre directement dans la méthode SearchBooks, vous ne pouvez pas voir JsonData.cs sous **Modifications**.

1. Utilisez GitHub Copilot pour générer un message pour le **Commit**.

1. Pour indexer et commiter les modifications, sélectionnez **Commiter**, puis **Oui**.

1. Synchronisez (ou envoyez (push)) vos modifications avec le dépôt distant.

    Si nécessaire, utilisez votre compte GitHub pour authentifier et autoriser la synchronisation.

#### Tâche 3 : créer une demande de tirage (pull request) pour fusionner vos modifications dans la branche primaire du référentiel

Vous pouvez utiliser une demande de tirage (pull request) pour fusionner vos modifications dans la branche primaire du référentiel. Après avoir créé une demande de tirage (pull request), vous pouvez passer en revue les modifications, vérifier que les vérifications réussissent, puis fusionner les modifications dans la branche primaire. GitHub Copilot peut vous aider à générer un résumé de la demande de tirage pour aider les réviseurs à comprendre vos modifications.

Utilisez les étapes suivantes pour terminer cette section de l’exercice :

1. Ouvrez votre dépôt GitHub dans un navigateur web.

1. Ouvrez l’onglet **Demandes de tirage**.

1. Sélectionnez **New pull request**.

1. Sous **Comparer les modifications**, vérifiez que **base** est configuré pour la branche **main**.

1. Vérifiez que **compare** est configuré pour la branche **book-availability**.

    Une fois que vous avez configuré les branches, une comparaison des modifications entre **main** et **book-availability** s’affiche. Vous devez voir les modifications apportées aux fichiers CommonActions.cs, ConsoleApp.cs et JsonDaa.cs.

1. Sélectionnez **Create pull request**.

1. Entrez un titre pour la demande de tirage.

    Les membres d’une entreprise disposant d’un abonnement à GitHub Copilot Enterprise peuvent utiliser GitHub Copilot pour générer un résumé descriptif d’une demande de tirage. Le résumé détaillé aide les réviseurs à comprendre vos modifications.

1. Utilisez GitHub Copilot pour générer un résumé d’une demande de tirage.

    Pour générer le résumé, sélectionnez le bouton Actions Copilot, puis sélectionnez **Résumé**.

    Vous pouvez utiliser l’onglet Aperçu pour passer en revue le résumé de la demande de tirage (pull request) générée par GitHub Copilot.

1. Vérifiez que le titre et la description reflètent vos mises à jour de code, puis sélectionnez **Créer une demande de tirage**.

1. Attendez que les contrôles se terminent, puis vérifiez que tous les contrôles ont réussi et qu’il n’y a aucun conflit avec la branche de base.

    L’exécution des contrôles peut prendre une minute. Vous devez résoudre les problèmes identifiés avant de pouvoir fusionner les modifications dans la branche principale.

1. Pour fusionner vos modifications dans la branche principale, sélectionnez **Fusionner la demande de tirage**, puis **Confirmer la fusion**.

    Notez que vous pouvez supprimer la branche book-availability après avoir fusionné les modifications.

1. Ouvrez Visual Studio Code.

1. Basculez vers la branche **main** du dépôt.

1. **Tirez (pull)** les modifications à partir du dépôt distant.

    Si vous y êtes invité, utilisez votre compte GitHub pour authentifier et autoriser le tirage.

1. Vérifiez que les modifications que vous avez apportées dans la branche **book-availability** se trouvent désormais dans la branche **main**.

    Les modifications apportées aux fichiers CommonActions.cs et ConsoleApp.cs doivent être présentes dans la branche primaire.

#### Résumé - Exercice 6

Dans cet exercice, vous avez testé votre code, puis fusionné vos modifications dans la branche primaire du référentiel. Vous avez implémenté vos modifications dans le référentiel local, les avez synchronisées avec le référentiel distant, puis créé une demande de tirage (pull request) pour fusionner vos modifications dans la branche primaire du référentiel. Vous avez utilisé GitHub Copilot pour générer un résumé de la demande de tirage pour aider les réviseurs à comprendre vos modifications.

## Partie 3 : développer des tests unitaires à l’aide des outils GitHub Copilot

### Avant de commencer

#### Vue d'ensemble du projet

Votre collègue a créé un projet de test nommé UnitTests. Les tests unitaires existants couvrent partiellement les classes de service dans le projet Library.ApplicationCore. Le projet Library.ApplicationCore contient la logique métier d’un système de gestion de bibliothèque. Le projet UnitTests utilise l’infrastructure xUnit pour écrire et exécuter des tests unitaires. Le projet utilise également la bibliothèque NSubstitute pour créer des objets de simulation à des fins de test.

Vous devez étendre le projet UnitTests pour couvrir les classes d’accès aux données dans le projet Library.Infrastructure.

#### Scénario de labo (partie 3)

GitHub Copilot peut vous aider à écrire des tests unitaires pour votre code. Il existe plusieurs façons d’utiliser GitHub Copilot pour générer des tests unitaires :

- **Générer des cas de test** : Vous pouvez utiliser GitHub Copilot afin de générer des cas de test pour votre code. Copilot peut suggérer des cas de test basés sur le code que vous avez écrit. Vous pouvez ensuite utiliser ces cas de test pour créer des tests unitaires pour votre code.
- **Générer des méthodes de test** : Copilot peut également générer des méthodes de test pour votre code. Vous pouvez utiliser ces méthodes de test pour créer des tests unitaires pour votre code.
- **Générer des assertions de test** : Copilot peut suggérer des assertions que vous pouvez utiliser dans vos tests unitaires. Ces assertions peuvent vous aider à vérifier le comportement de votre code.
- **Générer des simulations de test** : Copilot peut générer des objets de simulation que vous pouvez utiliser dans vos tests unitaires. Ces objets de simulation peuvent vous aider à isoler le code que vous testez de ses dépendances.
- **Générer des données de test** : Copilot peut générer des données de test que vous pouvez utiliser dans vos tests unitaires. Ces données de test peuvent vous aider à tester votre code avec différentes entrées.
- **Générer du code d’initialisation de test** : Copilot peut générer du code d’initialisation pour vos tests unitaires. Ce code peut vous aider à configurer l’environnement de test avant d’exécuter vos tests.
- **Générer du code de désactivation de test** : Copilot peut générer du code de désactivation pour vos tests unitaires. Ce code peut vous aider à nettoyer l’environnement de test après avoir exécuté vos tests.

Dans la partie 3 de ce labo, vous développez des tests unitaires pour le projet Library.Infrastructure.

Cette partie inclut l’exercice suivant :

- Utiliser GitHub Copilot pour évaluer et étendre le projet UnitTests.

### Exercice 7 : utiliser GitHub Copilot pour évaluer et étendre le projet UnitTests

Dans cet exercice, vous utilisez GitHub Copilot pour accomplir les tâches suivantes :

1. Utiliser GitHub Copilot pour évaluer le projet UnitTests existant.

1. Étendre le projet UnitTests pour commencer à tester les classes d’accès aux données.

#### Tâche 1 : utiliser GitHub Copilot pour évaluer le projet UnitTests existant

Le projet UnitTests implémente actuellement la structure de dossiers suivante :

- UnitTests\
  - ApplicationCore\
    - LoanService\
      - ExtendLoan.cs
      - ReturnLoan.cs
    - PatronService\
      - RenewMembership.cs
  - LoanFactory.cs
  - PatronFactory.cs

Cette structure reflète et prend en charge la partie du projet ApplicationCore.

- ApplicationCore\
  - Services\
    - LoanService.cs : contient les méthodes ExtendLoan et ReturnLoan.
    - PatronService.cs : contient la méthode RenewMembership.

L’évaluation des tests unitaires existants vous aidera à développer des tests unitaires pour les classes d’accès aux données dans le projet Library.Infrastructure.

Utilisez les étapes suivantes pour terminer cette section de l’exercice :

1. Fermez tous les fichiers que vous avez ouverts dans l’éditeur.

1. Ouvrez l’affichage Conversation.

1. Ajoutez les fichiers suivants au contexte Conversation : **LoanFactory.cs**, **PatronFactory.cs**, **ExtendLoan.cs**, **ReturnLoan.cs**, **RenewMembership.cs**, **LoanService.cs**, **PatronService.cs**.

    Les fichiers se trouvent dans les dossiers « tests/UnitTests », « tests/UnitTests/ApplicationCore/LoanService », « tests/UnitTests/ApplicationCore/PatronService » et « src/Library.ApplicationCore/Services ».

1. Entrez l’invite suivante :

    ```plaintext
    @workspace Explain the approach to unit testing that's been implemented in this workspace.
    ```

    Ce prompt demande à GitHub Copilot d’expliquer l’approche de réalisation des tests unitaires dans le contexte de l’espace de travail. Plusieurs fichiers sont inclus dans le prompt afin de fournir le contexte pour la réponse.

1. Prenez une minute pour passer en revue la réponse de GitHub Copilot.

    Vous devriez voir une explication similaire à la description suivante :

    - Dépendances simulées : les tests utilisent NSubstitute pour créer des implémentations simulées des interfaces.
    - Organisation des tests : Les tests sont organisés sous forme de fichiers distincts selon les méthodes testées. Par exemple, les méthodes ExtendLoan et ReturnLoan sont testées dans des fichiers distincts sous le dossier LoanService.
    - Assertions : Les assertions sont utilisées pour vérifier le résultat attendu de chaque test.
    - Scénarios de test : Les tests couvrent divers scénarios pour chaque méthode, tels que le retour d’états différents en fonction de l’entrée.
    - Isolation : Chaque test est isolé des autres pour empêcher les effets secondaires.
    - Méthodes de fabrique : Les méthodes de fabrique sont utilisées pour créer des données de test de manière cohérente.

1. Entrez l’invite suivante :

    ```plaintext
    @workspace What are the benefits of this approach to unit testing?
    ```

1. Prenez une minute pour passer en revue la réponse de GitHub Copilot.

    Vous devriez voir une explication qui identifie une liste d’avantages similaires à la liste suivante :

    - Isolation des dépendances : L’utilisation de simulations isole l’unité de travail de ses dépendances.
    - Reproductibilité et cohérence : Les méthodes de fabrique offrent un moyen cohérent de créer des données de test.
    - Lisibilité et maintenabilité : Des méthodes de test descriptives et une organisation claire des étapes de test améliorent la lisibilité des tests.
    - Couverture complète : Le test de divers scénarios permet de garantir la robustesse du code et de gérer différents cas limite.
    - Séparation des responsabilités : La séparation de la création de données de test de la logique de test elle-même permet de garder des tests propres et de se concentrer sur le comportement en cours de test.
    - Retours immédiats : L’exécution de tests unitaires fournit des retours immédiats sur l’exactitude du code.

1. Ajoutez les fichiers suivants au contexte Conversation : **ExtendLoan.cs**, **ReturnLoan.cs**, **RenewMembership.cs**, **LoanFactory.cs**, **PatronFactory.cs**, **LoanService.cs**, **PatronService.cs**.

1. Entrez l’invite suivante :

    ```plaintext
    @workspace How can I extend the `UnitTests` project to begin testing methods in the `Library.Infrastructure` project? Provide a process overview.
    ```

    Cette invite demande à GitHub Copilot de fournir une vue d’ensemble du processus permettant d’étendre le projet UnitTests pour commencer à tester les méthodes dans le projet Library.Infrastructure. Plusieurs fichiers sont inclus dans le prompt afin de fournir le contexte pour la réponse.

1. Prenez une minute pour passer en revue la réponse de GitHub Copilot.

    Vous devriez voir une explication similaire à la description suivante :

    ```markdown
    1. Add Project Reference:

      - Open the UnitTests.csproj file located at tests/UnitTests/UnitTests.csproj.
      - Add a reference to the Library.Infrastructure project.

    2. Identify methods to test:

      - Identify the methods in the Library.Infrastructure project that need to be tested. For example, if you want to test the LoanService class, identify the methods in the LoanService class that need to be tested.

    3. Create Test Classes:

      - Create new test classes in the tests/UnitTests directory to test the methods in the Library.Infrastructure project. For example, if you want to test LoanService, create a file named LoanServiceTests.cs.

    4. Write Unit Tests:

      - In the newly created test classes, write unit tests for the methods in the Library.Infrastructure project. Use the xUnit framework for writing tests and NSubstitute for mocking dependencies.

    5. Run Tests:

      - Use Visual Studio Code's integrated terminal or the Test Explorer to run the tests.
      - Ensure that the tests are discovered and executed correctly.
    ```

#### Tâche 2 : étendre le projet UnitTests pour commencer à tester les classes d’accès aux données

Dans cette section de l’exercice, vous utilisez GitHub Copilot pour vous aider à créer des tests unitaires pour le projet Library.Infrastructure.

Le projet Library.Infrastructure contient des classes d’accès aux données qui interagissent avec le système de fichiers pour charger et enregistrer des données. Le projet inclut les classes suivantes :

- JsonData : Classe qui charge et enregistre des données JSON.
- JsonLoanRepository : Classe qui implémente l’interface ILoanRepository et utilise la classe JsonData pour charger et enregistrer les données de prêt.
- JsonPatronRepository : Classe qui implémente l’interface IPatronRepository et utilise la classe JsonData pour charger et enregistrer les données d’adhérent.

Vous allez commencer par écrire les tests unitaires pour la classe JsonLoanRepository.

Utilisez les étapes suivantes pour terminer cette section de l’exercice :

1. Ajoutez le fichier projet suivant au contexte Conversation : **UnitTests.csproj**.

1. Entrez le prompt suivant dans la vue Conversation :

    ```plaintext
    @workspace Explain how to add a reference to the Library.Infrastructure project inside `UnitTests.csproj`.
    ```

    Ce prompt demande à GitHub Copilot d’expliquer comment ajouter une référence au projet Library.Infrastructure dans le fichier UnitTests.csproj.

1. Utilisez la réponse GitHub Copilot pour mettre à jour le fichier UnitTests.csproj.

    Le fichier UnitTests.csproj mis à jour devrait ressembler au code XML suivant :

    ```xml

    <Project Sdk="Microsoft.NET.Sdk">
      <PropertyGroup>
        <TargetFramework>net8.0</TargetFramework>
        <ImplicitUsings>enable</ImplicitUsings>
        <Nullable>enable</Nullable>
        <IsPackable>false</IsPackable>
        <IsTestProject>true</IsTestProject>
      </PropertyGroup>
      <ItemGroup>
        <PackageReference Include="coverlet.collector" Version="6.0.0" />
        <PackageReference Include="Microsoft.NET.Test.Sdk" Version="17.8.0" />
        <PackageReference Include="NSubstitute" Version="5.1.0" />
        <PackageReference Include="xunit" Version="2.5.3" />
        <PackageReference Include="xunit.runner.visualstudio" Version="2.5.3" />
      </ItemGroup>
      <ItemGroup>
        <Using Include="Xunit" />
      </ItemGroup>
      <ItemGroup>
        <ProjectReference Include="..\..\src\Library.ApplicationCore\Library.ApplicationCore.csproj" />
        <ProjectReference Include="..\..\src\Library.Infrastructure\Library.Infrastructure.csproj" />
      </ItemGroup>
    </Project>

    ```

1. Ouvrez le fichier **JsonLoanRepository.cs**.

    JsonLoanRepository.cs se trouve dans le dossier « src/Library.Infrastructure/Data/ ».

1. Prenez quelques instants pour passer en revue le fichier **JsonLoanRepository.cs**.

    ```csharp

    using Library.ApplicationCore;
    using Library.ApplicationCore.Entities;
    namespace Library.Infrastructure.Data;
    public class JsonLoanRepository : ILoanRepository
    {
        private readonly JsonData _jsonData;
        public JsonLoanRepository(JsonData jsonData)
        {
            _jsonData = jsonData;
        }
        public async Task<Loan?> GetLoan(int id)
        {
            await _jsonData.EnsureDataLoaded();
    
            foreach (Loan loan in _jsonData.Loans!)
            {
                if (loan.Id == id)
                {
                    Loan populated = _jsonData.GetPopulatedLoan(loan);
                    return populated;
                }
            }
            return null;
        }
        public async Task UpdateLoan(Loan loan)
        {
            Loan? existingLoan = null;
            foreach (Loan l in _jsonData.Loans!)
            {
                if (l.Id == loan.Id)
                {
                    existingLoan = l;
                    break;
                }
            }
            if (existingLoan != null)
            {
                existingLoan.BookItemId = loan.BookItemId;
                existingLoan.PatronId = loan.PatronId;
                existingLoan.LoanDate = loan.LoanDate;
                existingLoan.DueDate = loan.DueDate;
                existingLoan.ReturnDate = loan.ReturnDate;
                await _jsonData.SaveLoans(_jsonData.Loans!);
                await _jsonData.LoadData();
            }
        }
    }

    ```

1. Notez les détails suivants sur la classe **JsonLoanRepository** :

    - La classe JsonLoanRepository contient deux méthodes : GetLoan et UpdateLoan.
    - La classe JsonLoanRepository utilise un objet JsonData pour charger et enregistrer les données de prêt.

    Vous allez commencer par écrire les tests unitaires pour la méthode GetLoan.

1. Créez la structure de dossiers suivante sous le projet **UnitTests**.

    - Infrastructure\
        - JsonLoanRepository\

    Cette structure de dossiers reflète l’approche utilisée pour les tests unitaires Library.ApplicationCore.

1. Créez un fichier de classe nommé **GetLoan** dans le dossier JsonLoanRepository.

1. Prenez quelques instants afin d’examiner les constructeurs de champ et de classe requis pour les tests unitaires GetLoan.

    La méthode JsonLoanRepository.GetLoan reçoit un paramètre d’ID de prêt lorsqu’elle est appelée. La méthode utilise « _jsonData.EnsureDataLoaded » pour obtenir les données JSON les plus récentes et « _jsonData.Loans » pour rechercher un prêt correspondant. Si la méthode trouve un ID de prêt correspondante, elle retourne un objet de prêt renseigné (populated). Si la méthode n’arrive pas à trouver un ID de prêt correspondant, elle retourne null.

    Pour les tests unitaires GetLoan :

    - Vous pouvez utiliser un objet de référentiel de prêt simulé (« _mockLoanRepository ») pour pouvoir tester le cas où un ID correspondant est trouvé. Chargez la simulation avec la référence que vous souhaitez rechercher. La classe ReturnLoanTest montre comment simuler l’interface ILoanRepository et instancier un objet de référentiel de prêt simulé.

    - Vous pouvez utiliser un objet de référentiel de prêt non simulé (« _jsonLoanRepository ») pour tester le cas où aucune référence correspondante n’est trouvée. Spécifiez juste une référence de prêt que vous savez n’est pas dans le fichier (tout nombre supérieur à 100 devrait fonctionner).

    - Vous aurez besoin d’un objet JsonData pour créer un objet JsonLoanRepository non simulé. Étant donné que le projet UnitTests n’a pas accès à l’objet JsonData créé par le projet ConsoleApp, vous devez en créer un en utilisant l’interface IConfiguration.

1. Ajoutez les fichiers suivants au contexte Conversation : **JsonLoanRepository.cs**, **ReturnLoan.cs**, **LoanService.cs**, **LoanFactory.cs**, **JsonData.cs**.

1. Entrez l’invite suivante :

    ```plaintext
    @workspace Create fields and a class constructor for the `GetLoan.cs` file. The class will be used to create unit tests for the GetLoan method in the `JsonLoanRepository.cs` file. Create the following private readonly fields: `_mockLoanRepository`, `_jsonLoanRepository`, `_configuration`, and `_jsonData`. Instantiate the fields in the `GetLoanTest` constructor. Use `ConfigurationBuilder` to create a `_configuration` object that can be used to instantiate the JsonData object.
    ```

    Ce prompt demande à GitHub Copilot de suggérer des champs et un constructeur de classe.

1. Prenez une minute pour passer en revue la réponse de GitHub Copilot.

    Vous devriez voir une suggestion de code similaire à l’extrait de code suivant :

    ```csharp

    using NSubstitute;
    using Library.ApplicationCore;
    using Library.ApplicationCore.Entities;
    using Library.ApplicationCore.Interfaces;
    using Library.Infrastructure.Data;
    using Microsoft.Extensions.Configuration;
    namespace UnitTests.Infrastructure.JsonLoanRepository;
    public class GetLoanTest
    {
        private readonly ILoanRepository _mockLoanRepository;
        private readonly JsonLoanRepository _jsonLoanRepository;
        private readonly IConfiguration _configuration;
        private readonly JsonData _jsonData;
        public GetLoanTest()
        {
            _mockLoanRepository = Substitute.For<ILoanRepository>();
            _configuration = new ConfigurationBuilder()
                .AddJsonFile("appsettings.json")
                .Build();
            _jsonData = new JsonData(_configuration);
            _jsonLoanRepository = new JsonLoanRepository(_jsonData);
        }
        // Add test methods here
    }

    ```

1. Utilisez la suggestion de code fournie par GitHub Copilot pour mettre à jour **GetLoan.cs**.

1. Notez les problèmes suivants :

    - Un conflit existe entre l’espace de noms et l’utilisation de JsonLoanRepository dans le code. Vous devez mettre à jour l’espace de noms dans GetLoans.cs pour suivre le modèle utilisé dans les fichiers ReturnLoan.cs et RenewMembership.cs.

    - Si ILoanRepository n’est pas reconnu dans votre code, vous devrez peut-être ajouter une directive using pour Library.ApplicationCore en haut du fichier.

    - Si l’objet _configuration n’est pas instancié correctement, vous devrez peut-être mettre à jour la ligne de code contenant ConfigurationBuilder. Vous pouvez simplifier le code pour qu’il utilise « _configuration = new ConfigurationBuilder(). Build(); ».

    - Si un message « using Library.ApplicationCore.Interfaces » est suggéré par GitHub Copilot, vous pouvez le supprimer du haut du fichier.

1. Mettez à jour le fichier **GetLoan.cs** pour qu’il corresponde à l’extrait de code suivant :

    ```csharp

    using NSubstitute;
    using Library.ApplicationCore;
    using Library.ApplicationCore.Entities;
    using Library.Infrastructure.Data;
    using Microsoft.Extensions.Configuration;
    namespace UnitTests.Infrastructure.JsonLoanRepositoryTests;
    public class GetLoanTest
    {
        private readonly ILoanRepository _mockLoanRepository;
        private readonly JsonLoanRepository _jsonLoanRepository;
        private readonly IConfiguration _configuration;
        private readonly JsonData _jsonData;
        public GetLoanTest()
        {
            _mockLoanRepository = Substitute.For<ILoanRepository>();
            _configuration = new ConfigurationBuilder().Build();
            _jsonData = new JsonData(_configuration);
            _jsonLoanRepository = new JsonLoanRepository(_jsonData);
        }
    }

    ```

    Les mises à jour de code corrigent les problèmes identifiés à l’étape précédente. La création du projet résout les problèmes identifiés dans l’éditeur.

1. Ajoutez les fichiers suivants au contexte Conversation : **JsonLoanRepository.cs**, **ReturnLoan.cs**, **LoanService.cs**, **LoanFactory.cs**, **JsonData.cs**, **Loans.json**.

1. Sélectionnez le contenu du fichier GetLoan.cs et entrez l’invite suivante dans la vue Conversation :

    ```plaintext
    @workspace Update the selection to include a unit test for the `JsonLoanRepository.GetLoan` method. The unit test should test the case where a loan ID is found in the data. Use `_mockLoanRepository` to arrange the expected return loan. Use `_jsonLoanRepository` to return an actual loan. Asserts should verify that the return loan ID matches the expected loan ID. Use a loan ID that exists in the `Loans.json` file.
    ```

    Cette invite demande à GitHub Copilot de suggérer un test unitaire pour la méthode JsonLoanRepository.GetLoan. Le test unitaire doit tester le cas où une référence de prêt est trouvée dans les données. Le test doit utiliser « _mockLoanRepository » pour organiser le prêt de retour attendu, « _jsonLoanRepository » pour retourner un vrai prêt et des assertions pour vérifier que l’ID de prêt retourné correspond à l’ID de prêt attendu. L’ID de prêt devrait se trouver dans le fichier Loans.json.

1. Prenez une minute pour passer en revue la réponse de GitHub Copilot.

    Vous devriez voir une suggestion de code similaire à l’extrait de code suivant :

    ```csharp

    using NSubstitute;
    using Library.ApplicationCore;
    using Library.ApplicationCore.Entities;
    using Library.Infrastructure.Data;
    using Microsoft.Extensions.Configuration;
    using Xunit;
    namespace UnitTests.Infrastructure.JsonLoanRepositoryTests;
    public class GetLoanTest
    {
        private readonly ILoanRepository _mockLoanRepository;
        private readonly JsonLoanRepository _jsonLoanRepository;
        private readonly IConfiguration _configuration;
        private readonly JsonData _jsonData;
        public GetLoanTest()
        {
            _mockLoanRepository = Substitute.For<ILoanRepository>();
            _configuration = new ConfigurationBuilder().Build();
            _jsonData = new JsonData(_configuration);
            _jsonLoanRepository = new JsonLoanRepository(_jsonData);
        }
        [Fact(DisplayName = "JsonLoanRepository.GetLoan: Returns loan when loan ID is found")]
        public async Task GetLoan_ReturnsLoanWhenLoanIdIsFound()
        {
            // Arrange
            var loanId = 1; // Use a loan ID that exists in the Loans.json file
            var expectedLoan = new Loan { Id = loanId, BookItemId = 101, PatronId = 202, LoanDate = DateTime.Now, DueDate = DateTime.Now.AddDays(14) };
            _mockLoanRepository.GetLoan(loanId).Returns(expectedLoan);
            await _jsonData.EnsureDataLoaded(); // Ensure data is loaded
            // Act
            var actualLoan = await _jsonLoanRepository.GetLoan(loanId);
            // Assert
            Assert.NotNull(actualLoan);
            Assert.Equal(expectedLoan.Id, actualLoan?.Id);
        }
    }

    ```

1. Utilisez la suggestion de code fournie par GitHub Copilot pour mettre à jour **GetLoan.cs**.

    La méthode JsonLoanRepository.GetLoan appelle « _jsonData.EnsureDataLoaded » pour s’assurer que les données JSON sont chargées. Vous pouvez supprimer la ligne de code qui appelle « _jsonData.EnsureDataLoaded » dans la méthode de test si elle s’y trouve.

    Si la classe Loan n’est pas reconnue dans votre code, vérifiez que vous disposez d’une instruction « using Library.ApplicationCore.Entities » en haut du fichier GetLoan.cs. La classe Loan se trouve dans l’espace de noms Library.ApplicationCore.Entities.

1. Générez la solution AccelerateDevGitHubCopilot pour vérifier qu’elle ne contient aucune erreur.

1. Utilisez la fonctionnalité d’autocomplétion de GitHub Copilot afin de créer un test pour le cas où la référence du prêt n’est pas trouvée.

    Créez une ligne vide après la méthode GetLoan_ReturnsLoanWhenLoanIdIsFound.

    Acceptez les suggestions d’autocomplétion pour créer une méthode de test.

1. Prenez une minute pour passer en revue la réponse de GitHub Copilot.

    La fonctionnalité d’autocomplétion de GitHub Copilot simulera probablement un prêt attendu, même si ce n’est pas nécessaire. Vous pouvez supprimer le code qui simule un prêt attendu, mais vous avez besoin d’un ID de prêt qui n’existe pas dans le fichier Loans.json.

    Vous devriez voir une suggestion de code similaire à l’un des extraits de code suivants :

    ```csharp

    [Fact(DisplayName = "JsonLoanRepository.GetLoan: Returns null when loan ID is not found")]
    public async Task GetLoan_ReturnsNullWhenLoanIdIsNotFound()
    {
        // Arrange
        var loanId = 999; // Use a loan ID that does not exist in the Loans.json file
        var expectedLoan = new Loan { Id = loanId, BookItemId = 101, PatronId = 202, LoanDate = DateTime.Now, DueDate = DateTime.Now.AddDays(14) };
        _mockLoanRepository.GetLoan(loanId).Returns(expectedLoan);
        // Act
        var actualLoan = await _jsonLoanRepository.GetLoan(loanId);
        // Assert
        Assert.Null(actualLoan);
    }

    ```

1. Acceptez la suggestion de saisie automatique qui affecte une valeur loanId absente du jeu de données.

    Si aucune des suggestions n’affecte des numéros loanId absents du jeu de données, vous pouvez utiliser le raccourci clavier **Ctrl+Entrée** pour lister des suggestions supplémentaires.

1. Notez que les tests unitaires ont besoin d’accéder aux fichiers de données JSON.

    La méthode JsonLoanRepository.GetLoan utilise un objet JsonData pour charger et enregistrer des données de prêt.

    Les fichiers de données JSON se trouvent dans le dossier « Library.Console\Json ». Vous devez mettre à jour le fichier UnitTests.csproj pour inclure ces fichiers dans le projet de test.

1. Ajoutez l’extrait de code XML suivant au fichier **UnitTests.csproj** :

    ```xml

    <ItemGroup>
        <None Include="..\..\src\Library.Console\Json\**\*">
            <Link>Json\%(RecursiveDir)%(FileName)%(Extension)</Link>
            <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
        </None>
    </ItemGroup>

    ```

    Cette opération permet de garantir que les fichiers de données JSON sont copiés dans le répertoire de sortie lorsque les tests sont exécutés.

#### Tâche 3 : vérifier votre travail

Il existe plusieurs façons d’exécuter les tests unitaires pour la classe JsonLoanRepository. Vous pouvez utiliser l’Explorateur de tests de Visual Studio Code, le terminal intégré ou la commande « dotnet test ».

Utilisez les étapes suivantes pour terminer cette section de l’exercice :

1. Assurez-vous que le fichier GetLoans.cs est ouvert dans l’éditeur.

1. Générez la solution et vérifiez qu’elle ne contient aucune erreur.

    Cliquez avec le bouton droit sur **AccelerateDevGitHubCopilot**, puis sélectionnez **Générer**.

1. Notez le « bouton de lecture vert » à gauche des méthodes de test.

1. Ouvrez la vue Explorateur de tests de Visual Studio Code.

    Pour ouvrir la vue Explorateur de tests, sélectionnez l’icône représentant un bécher dans la barre d’activité de gauche. L’Explorateur de tests est appelé « Test » dans l’interface utilisateur.

    L’Explorateur de tests est une arborescence qui montre tous les cas de test de votre espace de travail. Vous pouvez exécuter/déboguer vos cas de test et voir les résultats des tests en utilisant l’Explorateur de tests.

1. Développez **UnitTests** et les nœuds sous-jacents pour localiser **GetLoanTest**.

1. Exécutez le cas de test **JsonLoanRepository.GetLoan : Retourne le prêt lorsque la référence de prêt est trouvée**.

    > [!NOTE]
    > GitHub Copilot peut avoir nommé la méthode de test différemment. Exécutez la méthode de test qui utilise un ID de prêt existant dans les données.

1. Notez les résultats des tests dans la vue Explorateur de tests et dans l’Éditeur.

    Vous devriez voir une coche verte qui indique que le test a réussi.

1. Utilisez l’Éditeur pour exécuter le cas de test **JsonLoanRepository.GetLoan : Retourne une valeur nulle lorsque la référence de prêt n’est pas trouvée**.

1. Notez les résultats des tests dans la vue Explorateur de tests et dans l’Éditeur.

    Pour exécuter le test à partir de l’Éditeur, sélectionnez le bouton de lecture vert à gauche de la méthode de test.

1. Vérifiez que le test **JsonLoanRepository.GetLoan : Retourne une valeur nulle lorsque la référence de prêt n’est pas trouvée réussit**.

    Vous devriez voir une coche verte à gauche des deux tests.

#### Résumé - Exercice 7

Dans cet exercice, vous avez utilisé GitHub Copilot pour évaluer le projet UnitTests existant et étendre le projet pour commencer à tester les classes d’accès aux données dans le projet Library.Infrastructure. Vous avez ajouté une référence au projet Library.Infrastructure dans le fichier UnitTests.csproj et créé des tests unitaires pour la classe JsonLoanRepository. Vous avez utilisé GitHub Copilot afin de vous aider à écrire les tests unitaires pour la méthode GetLoan dans la classe JsonLoanRepository. Vous avez exécuté les tests unitaires à l’aide de l’Explorateur de tests de Visual Studio Code et vérifié que les tests ont réussi.

## Partie 4 : refactoriser et améliorer des sections de code en tirant parti des outils GitHub Copilot

### Avant de commencer

#### Vue d'ensemble du projet

Vous et votre collègue avez terminé la phase de développement initiale du projet et étudiez maintenant les façons de refactoriser et d’améliorer votre codebase.

La refactorisation du code est un processus qui restructure du code existant sans modifier son comportement externe. La refactorisation est souvent utilisée pour améliorer un aspect spécifique du code. GitHub Copilot peut vous aider à refactoriser votre code en suggérant des modifications qui améliorent la qualité, la fiabilité, les performances et la sécurité du code.

#### Scénario de labo (partie 4)

Dans la partie 4 de ce labo, vous utilisez GitHub Copilot pour refactoriser les sections de code suivantes :

- Vous refactorisez la classe EnumHelper de façon à utiliser des dictionnaires au lieu de la réflexion. L’utilisation de dictionnaires améliore les performances en réduisant la surcharge de réflexion. L’élimination de la réflexion améliore également la lisibilité, la facilité de maintenance et la sécurité du code.

- Vous refactorisez les méthodes d’accès aux données de façon à utiliser LINQ (Language Integrated Query) plutôt que des boucles foreach. L’utilisation de LINQ offre un moyen plus concis et lisible d’interroger des collections, des bases de données et des documents XML. L’utilisation de LINQ peut améliorer la lisibilité, la facilité de maintenance et les performances du code.

La partie inclut les exercices suivants :

- Utiliser GitHub Copilot pour refactoriser la classe EnumHelper.
- Utiliser GitHub Copilot pour améliorer les classes d’accès aux données avec LINQ.

### Exercice 8 : utiliser GitHub Copilot pour refactoriser la classe EnumHelper

La réflexion est une fonctionnalité puissante qui vous permet d’inspecter et de manipuler des objets au moment de l’exécution. Toutefois, la réflexion peut être lente, et il existe des risques de sécurité potentiels associés à la réflexion qui doivent être pris en compte.

La classe EnumHelper existante utilise la réflexion pour récupérer l’attribut de description d’une valeur d’énumération. Vous pouvez refactoriser la classe EnumHelper de façon à utiliser des dictionnaires au lieu de la réflexion. L’utilisation de dictionnaires peut améliorer les performances et éliminer les problèmes de sécurité associés à l’utilisation de la réflexion.

Dans cet exercice, vous utilisez GitHub Copilot pour vous aider à refactoriser la classe EnumHelper.

Pour effectuer cet exercice, procédez comme suit :

1. Utilisez la vue Explorateur de solutions pour ouvrir le fichier EnumHelper.cs.

    EnumHelper.cs se trouve dans le dossier « src/Library.ApplicationCore/Enums ».

    ```csharp

    using System.ComponentModel;
    using System.Reflection;
    namespace Library.ApplicationCore.Enums;
    public static class EnumHelper
    {
        public static string GetDescription(Enum value)
        {
            if (value == null)
                return string.Empty;
            FieldInfo fieldInfo = value.GetType().GetField(value.ToString())!;
            DescriptionAttribute[] attributes =
                (DescriptionAttribute[])fieldInfo.GetCustomAttributes(typeof(DescriptionAttribute), false);
            if (attributes != null && attributes.Length > 0)
            {
                return attributes[0].Description;
            }
            else
            {
                return value.ToString();
            }
        }
    }

    ```

1. Ouvrez la vue Conversation, puis ajoutez les fichiers suivants au contexte Conversation : **EnumHelper.cs**, **LoanExtensionStatus.cs**, **LoanReturnStatus.cs**, **MembershipRenewalStatus.cs**.

1. Entrez l’invite suivante :

    ```plaintext
    @workspace I want to refactor the `EnumHelper` class using dictionaries rather than reflection to get enum description attributes. I want a separate dictionary for each enum. The enum values are in the `LoanExtensionStatus.cs`, `LoanReturnStatus.cs`, and `MembershipRenewalStatus.cs` files. Explain how to update the EnumHelper class to use dictionaries and provide the updated code.
    ```

    Ce prompt demande à GitHub Copilot de fournir une explication indiquant comment mettre à jour la classe EnumHelper de façon à utiliser des dictionnaires plutôt que la réflexion. Il demande également le code mis à jour qui utilise des dictionnaires pour chaque valeur d’énumération.

1. Prenez un moment pour examiner les explications fournies par GitHub Copilot.

    L’explication doit être similaire à la suivante :

    ```markdown
    To refactor the EnumHelper class to use dictionaries for each enum, you need to create a dictionary for each enum type that maps the enum values to their descriptions. This will eliminate the need for reflection at runtime.

    Here's how you can update the EnumHelper class:

    1. Create dictionaries for each enum type.
    2. Populate these dictionaries with the enum values and their corresponding descriptions.
    3. Update the GetDescription method to use these dictionaries.

    Below is the updated code for the EnumHelper class:

    ```

    ```csharp

    using System.ComponentModel;
    using System.Collections.Generic;
    namespace Library.ApplicationCore.Enums
    {
        public static class EnumHelper
        {
            private static readonly Dictionary<MembershipRenewalStatus, string> MembershipRenewalStatusDescriptions = new()
            {
                { MembershipRenewalStatus.Success, "Membership renewal was successful." },
                { MembershipRenewalStatus.PatronNotFound, "Patron not found." },
                { MembershipRenewalStatus.TooEarlyToRenew, "It is too early to renew the membership." },
                { MembershipRenewalStatus.LoanNotReturned, "Cannot renew membership due to an outstanding loan." },
                { MembershipRenewalStatus.Error, "Cannot renew membership due to an error." }
            };
            private static readonly Dictionary<LoanReturnStatus, string> LoanReturnStatusDescriptions = new()
            {
                { LoanReturnStatus.Success, "Book was successfully returned." },
                { LoanReturnStatus.LoanNotFound, "Loan not found." },
                { LoanReturnStatus.AlreadyReturned, "Cannot return book as the book is already returned." },
                { LoanReturnStatus.Error, "Cannot return book due to an error." }
            };
            private static readonly Dictionary<LoanExtensionStatus, string> LoanExtensionStatusDescriptions = new()
            {
                { LoanExtensionStatus.Success, "Book loan extension was successful." },
                { LoanExtensionStatus.LoanNotFound, "Loan not found." },
                { LoanExtensionStatus.LoanExpired, "Cannot extend book loan as it already has expired. Return the book instead." },
                { LoanExtensionStatus.MembershipExpired, "Cannot extend book loan due to expired patron's membership." },
                { LoanExtensionStatus.LoanReturned, "Cannot extend book loan as the book is already returned." },
                { LoanExtensionStatus.Error, "Cannot extend book loan due to an error." }
            };
            public static string GetDescription(Enum value)
            {
                if (value == null)
                    return string.Empty;
                return value switch
                {
                    MembershipRenewalStatus status => MembershipRenewalStatusDescriptions[status],
                    LoanReturnStatus status => LoanReturnStatusDescriptions[status],
                    LoanExtensionStatus status => LoanExtensionStatusDescriptions[status],
                    _ => value.ToString()
                };
            }
        }
    }

    ```

    ```markdown

    This refactored EnumHelper class uses dictionaries to store the descriptions for each enum type. The GetDescription method now uses pattern matching to determine the type of the enum and retrieves the description from the appropriate dictionary. This approach avoids the use of reflection and improves performance.

    ```

    > [!NOTE]
    > Si GitHub Copilot ne remplit pas les dictionnaires avec les descriptions correctes, vérifiez que l’extension GitHub Copilot ne demande pas de redémarrage. Si c’est le cas, redémarrez l’extension et réessayez le prompt.

1. Utilisez la classe EnumHelper suggérée de GitHub Copilot pour mettre à jour votre fichier EnumHelper.cs.

1. Vérifiez que votre classe EnumHelper mise à jour utilise les valeurs d’énumération des fichiers LoanExtensionStatus.cs, LoanReturnStatus.cs et MembershipRenewalStatus.cs.

    Ouvrez chacun des fichiers d’énumération et vérifiez que les valeurs d’énumération dans les dictionnaires sont correctes. En cas d’incohérences, GitHub Copilot met à jour les dictionnaires pour chaque énumération individuellement. Par exemple, vous pouvez utiliser l’invite suivante pour l’énumération LoanExtensionStatus :

    ```plaintext
    @workspace Use the description values in LoanExtensionStatus.cs to update the LoanExtensionStatus dictionary in the EnumHelper class. Provide the updated code for the LoanExtensionStatus dictionary in the EnumHelper class.
    ```

    Si nécessaire, utilisez la même approche pour les énumérations LoanReturnStatus et MembershipRenewalStatus.

1. Prenez quelques instants pour passer en revue la méthode **GetDescription**.

    ```csharp

    public static string GetDescription(Enum value)
    {
        if (value == null)
            return string.Empty;
        return value switch
        {
            MembershipRenewalStatus status => MembershipRenewalStatusDescriptions[status],
            LoanReturnStatus status => LoanReturnStatusDescriptions[status],
            LoanExtensionStatus status => LoanExtensionStatusDescriptions[status],
            _ => value.ToString()
        };
    }

    ```

    Ce code utilise les critères spéciaux pour déterminer le type de l’énumération et récupérer la description à partir du dictionnaire approprié. L’instruction switch vérifie la valeur du type de l’énumération et retourne la description correspondante à partir du dictionnaire. Si la valeur d’énumération est introuvable dans le dictionnaire, la méthode retourne la valeur d’énumération sous forme de chaîne.

    Si vous demandez à GitHub Copilot de refactoriser ce code et d’éliminer les expressions lambda, sa lecture devient plus facile :

    ```csharp

    public static string GetDescription(Enum value)
    {
        if (value == null)
            return string.Empty;
        switch (value)
        {
            case MembershipRenewalStatus status:
                return MembershipRenewalStatusDescriptions[status];
            case LoanReturnStatus status:
                return LoanReturnStatusDescriptions[status];
            case LoanExtensionStatus status:
                return LoanExtensionStatusDescriptions[status];
            default:
                return value.ToString();
        }
    }

    ```

1. Enregistrez les modifications apportées à votre fichier EnumHelper.cs.

1. Générez votre solution afin de vérifier qu’il n’y a aucune erreur.

    Vous verrez des avertissements. Vous pouvez les ignorer pour le moment.

#### Résumé - Exercice 8

Dans cet exercice, vous avez utilisé GitHub Copilot pour refactoriser la classe EnumHelper de façon à utiliser des dictionnaires au lieu de la réflexion. L’utilisation de dictionnaires améliore les performances en réduisant la surcharge de réflexion. L’élimination de la réflexion améliore également la lisibilité, la facilité de maintenance et la sécurité du code.

### Exercice 9 : utiliser GitHub Copilot pour améliorer les classes d’accès aux données avec LINQ

LINQ (Language Integrated Query) est une fonctionnalité puissante en C# qui vous permet d’interroger des collections, des bases de données et des documents XML de manière uniforme. LINQ fournit un moyen plus concis et lisible d’interroger des données, par rapport aux boucles foreach traditionnelles.

Cet exercice comprend les tâches suivantes :

- Refactoriser les méthodes dans JsonData.cs de façon à utiliser LINQ.
- Refactoriser les méthodes dans JsonLoanRepository.cs de façon à utiliser LINQ.
- Refactoriser les méthodes dans JsonPatronRepository.cs de façon à utiliser LINQ.

#### Tâche 1 : refactoriser les méthodes dans JsonData.cs de façon à utiliser LINQ

La classe JsonData inclut les méthodes d’accès aux données suivantes : GetPopulatedPatron, GetPopulatedLoan, GetPopulatedBookItem, GetPopulatedBook. Ces méthodes utilisent des boucles foreach pour parcourir des collections et remplir des objets. Vous pouvez refactoriser ces méthodes de façon à utiliser LINQ pour améliorer la lisibilité et la maintenance du code.

Utilisez les étapes suivantes pour terminer cette section de l’exercice :

1. Ouvrez le fichier JsonData.cs.

1. Sélectionnez la méthode **GetPopulatedPatron**.

    La méthode GetPopulatedPatron est conçue pour créer un objet Patron entièrement rempli. Elle copie les propriétés de base de Patron, et remplit sa collection Loans avec des objets Loan détaillés.

    ```csharp

    public Patron GetPopulatedPatron(Patron p)
    {
        Patron populated = new Patron
        {
            Id = p.Id,
            Name = p.Name,
            ImageName = p.ImageName,
            MembershipStart = p.MembershipStart,
            MembershipEnd = p.MembershipEnd,
            Loans = new List<Loan>()
        };
        foreach (Loan loan in Loans!)
        {
            if (loan.PatronId == p.Id)
            {
                populated.Loans.Add(GetPopulatedLoan(loan));
            }
        }
        return populated;
    }

    ```

1. Ouvrez une conversation en ligne, puis entrez un prompt qui refactorise la méthode à l’aide de LINQ.

    ```plaintext
    #selection refactor selection to `return new Patron` using LINQ
    ```

1. Prenez une minute pour passer en revue la mise à jour suggérée.

    La mise à jour suggérée doit ressembler au code suivant :

    ```csharp

    public Patron GetPopulatedPatron(Patron p)
    {
        return new Patron
        {
            Id = p.Id,
            Name = p.Name,
            ImageName = p.ImageName,
            MembershipStart = p.MembershipStart,
            MembershipEnd = p.MembershipEnd,
            Loans = Loans!
                .Where(loan => loan.PatronId == p.Id)
                .Select(GetPopulatedLoan)
                .ToList()
        };
    }

    ```

    Tout d’abord, une requête LINQ est utilisée pour remplacer la boucle « foreach (Loan loan in Loans!) ». Avec le code LINQ en place, vous pouvez utiliser un initialiseur d’objet pour affecter des propriétés d’objet au nouvel objet Patron. Cela permet de réduire la nécessité d’une instance populated distincte de l’objet Patron. Dans l’ensemble, le code mis à jour est plus court et plus lisible.

    Le code utilise l’usager d’entrée « p » pour affecter certaines propriétés de base au nouvel objet Patron. Ensuite, il remplit la collection Loans avec des prêts associés à l’usager d’entrée, en transformant chaque prêt à l’aide de la méthode GetPopulatedLoan.

    Vous pouvez décomposer la ligne de code LINQ qui remplit la collection Loans :

    - `Loans!` : l’expression « Loans! » accède à la collection Loans. L’opérateur « ! » est un opérateur null-indulgent, indiquant que le développeur est sûr que Loans n’est pas Null. Vous devez vous assurer que Loans est correctement initialisé avant d’appeler la méthode GetPopulatedPatron.
    - `.Where(loan => loan.PatronId == p.Id)` : ce code filtre les prêts de façon à inclure uniquement ceux qui appartiennent à l’usager d’entrée « p ».
    - `.Select(GetPopulatedLoan)` : ce code transforme chaque prêt filtré à l’aide de la méthode GetPopulatedLoan.
    - `.ToList()` : convertit le résultat en une liste d’objets Loan.

1. Pour accepter la mise à jour suggérée, sélectionnez **Accepter**.

    Maintenant que vous avez vu comment refactoriser la méthode GetPopulatedPatron, vous pouvez refactoriser les méthodes GetPopulatedLoan, GetPopulatedBookItem et GetPopulatedBook de façon à utiliser également LINQ.

1. Refactorisez les méthodes **GetPopulatedLoan**, **GetPopulatedBookItem** et **GetPopulatedBook** à l’aide de la même approche.

    Par exemple, utilisez les prompts suivants pour refactoriser les trois méthodes :

    Pour la méthode **GetPopulatedLoan** :

    ```plaintext
    #selection refactor selection to `return new Loan` using LINQ. Use `GetPopulatedBookItem` for the `BookItem` property. Use `Single` for BookItem and Patron properties.
    ```

    Pour la méthode **GetPopulatedBookItem** :

    ```plaintext
    #selection refactor selection to `return new BookItem` using LINQ. Use `GetPopulatedBook` and `Single` for the `BookItem` property.
    ```

    Pour la méthode **GetPopulatedBook** :

    ```plaintext
    #selection refactor selection to `return new Book` using LINQ. Use `Where` and `Select` for `Author` property. Use `First` author.
    ```

1. Après avoir accepté les mises à jour suggérées, prenez une minute pour passer en revue vos modifications de code.

    Le code mis à jour doit ressembler au suivant :

    ```csharp

    public Loan GetPopulatedLoan(Loan l)
    {
        return new Loan
        {
            Id = l.Id,
            BookItemId = l.BookItemId,
            PatronId = l.PatronId,
            LoanDate = l.LoanDate,
            DueDate = l.DueDate,
            ReturnDate = l.ReturnDate,
            BookItem = GetPopulatedBookItem(BookItems!.Single(bi => bi.Id == l.BookItemId)),
            Patron = Patrons!.Single(p => p.Id == l.PatronId)
        };
    }
    public BookItem GetPopulatedBookItem(BookItem bi)
    {
        return new BookItem
        {
            Id = bi.Id,
            BookId = bi.BookId,
            AcquisitionDate = bi.AcquisitionDate,
            Condition = bi.Condition,
            Book = GetPopulatedBook(Books!.Single(b => b.Id == bi.BookId))
        };
    }
    public Book GetPopulatedBook(Book b)
    {
        return new Book
        {
            Id = b.Id,
            Title = b.Title,
            AuthorId = b.AuthorId,
            Genre = b.Genre,
            ISBN = b.ISBN,
            ImageName = b.ImageName,
            Author = Authors!.Where(a => a.Id == b.AuthorId).Select(a => new Author {
                Id = a.Id,
                Name = a.Name
            }).First()
        };
    }

    ```

1. Utilisez l’action intelligente **Expliquer** pour afficher une explication des requêtes LINQ.

    L’action intelligente **Expliquer** fournit une explication détaillée des requêtes LINQ utilisées dans le code.

    Par exemple, vous pouvez utiliser l’action intelligente **Expliquer** sur la méthode GetPopulatedBook afin d’afficher une explication de la requête LINQ utilisée pour remplir la propriété Author de l’objet Book.

    ```csharp

    Author = Authors!.Where(a => a.Id == b.AuthorId).Select(a => new Author {
        Id = a.Id,
        Name = a.Name
    }).First()

    ```

    L’action intelligente **Expliquer** fournit une explication détaillée de la requête LINQ utilisée pour remplir la propriété Author de l’objet Book.

    Par exemple, l’explication peut ressembler à ceci :

    ```plaintext
    The active selection is a C# code snippet that assigns a value to the Author property. This value is derived from a collection of Author objects named Authors. The code uses LINQ (Language Integrated Query) to filter and transform the data within this collection.
    
    First, the Authors! expression uses the null-forgiving operator (!) to indicate that Authors is not null, even if the compiler might think otherwise. This is a way to suppress nullable warnings. The Where method is then called on the Authors collection to filter the elements. The lambda expression a => a.Id == b.AuthorId is used to find all Author objects where the Id matches the AuthorId property of another object b.
    
    After filtering, the Select method is used to project each filtered Author object into a new Author object. This is done by creating a new instance of the Author class and copying the Id and Name properties from the original Author object.
    
    Finally, the First method is called to retrieve the first element from the resulting sequence. This means that the Author property will be assigned the first Author object that matches the filter criteria and has been projected into a new Author instance.
    
    This approach ensures that the Author property is set to a new Author object with the same Id and Name as the first matching Author in the Authors collection.
    ```

1. Enregistrez les modifications apportées au fichier JsonData.cs.

1. Générez votre solution afin de vérifier qu’il n’y a aucune erreur.

    Vous verrez des avertissements. Vous pouvez les ignorer pour le moment.

#### Tâche 2 : refactoriser les méthodes dans JsonLoanRepository.cs de façon à utiliser LINQ

La classe JsonLoanRepository inclut les méthodes d’accès aux données GetLoan et UpdateLoan. Vous allez refactoriser ces deux méthodes, en remplaçant les boucles foreach par LINQ pour améliorer la lisibilité et la maintenance du code.

Utilisez les étapes suivantes pour terminer cette section de l’exercice :

1. Ouvrez le fichier **JsonLoanRepository.cs**.

1. Sélectionnez la méthode **GetLoan**.

    La méthode GetLoan est conçue pour récupérer un prêt d’après son ID.

    ```csharp

    public async Task<Loan?> GetLoan(int id)
    {
        await _jsonData.EnsureDataLoaded();
        foreach (Loan loan in _jsonData.Loans!)
        {
            if (loan.Id == id)
            {
                Loan populated = _jsonData.GetPopulatedLoan(loan);
                return populated;
            }
        }
        return null;
    }

    ```

1. Ouvrez la conversation en ligne, puis entrez un prompt qui refactorise la méthode à l’aide de LINQ.

    Par exemple, entrez le prompt suivant :

    ```plaintext
    #selection refactor selection using LINQ with `_jsonData.Loans!. Use `Where`, `Select` and `GetPopulatedLoan` to return `FirstOrDefault`.
    ```

1. Prenez une minute pour passer en revue la mise à jour suggérée.

    La mise à jour suggérée doit ressembler au code suivant :

    ```csharp

    public async Task<Loan?> GetLoan(int id)
    {
        await _jsonData.EnsureDataLoaded();
        Loan? loan = _jsonData.Loans!
            .Where(l => l.Id == id)
            .Select(l => _jsonData.GetPopulatedLoan(l))
            .FirstOrDefault();
        return loan;
    }

    ```

    Le code mis à jour utilise LINQ pour filtrer la collection de prêts de façon à inclure uniquement le prêt avec l’ID spécifié. Notez que loan doit être déclaré comme nullable (`Loan? loan`). Ensuite, il transforme le prêt à l’aide de la méthode GetPopulatedLoan et retourne le premier résultat. Si aucun prêt correspondant n’est trouvé, FirstOrDefault retourne null. La méthode retourne ensuite cet objet loan, qui peut être null s’il n’existe aucun prêt avec l’ID spécifié. Cette approche garantit que le prêt retourné est entièrement rempli avec toutes les données associées nécessaires, fournissant une vue complète de l’enregistrement des prêts.

    Ce code peut être simplifié davantage :

    ```csharp

    public async Task<Loan?> GetLoan(int id)
    {
        await _jsonData.EnsureDataLoaded();
        return _jsonData.Loans!
            .Where(l => l.Id == id)
            .Select(l => _jsonData.GetPopulatedLoan(l))
            .FirstOrDefault();
    }

    ```

1. Pour accepter la méthode GetLoan mise à jour, sélectionnez **Accept**.

1. Sélectionnez la méthode **UpdateLoan**.

    ```csharp

    public async Task UpdateLoan(Loan loan)
    {
        Loan? existingLoan = null;
        foreach (Loan l in _jsonData.Loans!)
        {
            if (l.Id == loan.Id)
            {
                existingLoan = l;
                break;
            }
        }
        if (existingLoan != null)
        {
            existingLoan.BookItemId = loan.BookItemId;
            existingLoan.PatronId = loan.PatronId;
            existingLoan.LoanDate = loan.LoanDate;
            existingLoan.DueDate = loan.DueDate;
            existingLoan.ReturnDate = loan.ReturnDate;
            await _jsonData.SaveLoans(_jsonData.Loans!);
            await _jsonData.LoadData();
        }
    }

    ```

1. Ouvrez la conversation en ligne, puis entrez un prompt qui refactorise la méthode à l’aide de LINQ.

    Par exemple, entrez le prompt suivant :

    ```plaintext
    #selection refactor selection using LINQ find an existing loan `_jsonData.Loans!. Replace existing loan.
    ```

1. Prenez une minute pour passer en revue la mise à jour suggérée.

    La mise à jour suggérée doit ressembler au code suivant :

    ```csharp

    public async Task UpdateLoan(Loan loan)
    {
        Loan? existingLoan = _jsonData.Loans!.FirstOrDefault(l => l.Id == loan.Id);
        if (existingLoan != null)
        {
            existingLoan.BookItemId = loan.BookItemId;
            existingLoan.PatronId = loan.PatronId;
            existingLoan.LoanDate = loan.LoanDate;
            existingLoan.DueDate = loan.DueDate;
            existingLoan.ReturnDate = loan.ReturnDate;
            await _jsonData.SaveLoans(_jsonData.Loans!);
            await _jsonData.LoadData();
        }
    }

    ```

    Le code mis à jour utilise LINQ pour trouver le prêt existant dans la collection de prêts. Il met ensuite à jour le prêt existant avec les nouvelles données de prêt. La méthode enregistre ensuite la collection de prêts mise à jour, et recharge les données. Cette approche garantit que les données sur les prêts sont mises à jour correctement, et que les modifications sont conservées dans le magasin de données.

    Vous pouvez également ajouter le code pour vous assurer que les données sont chargées avant l’exécution de la méthode :

    ```csharp

    public async Task UpdateLoan(Loan loan)
    {
        await _jsonData.EnsureDataLoaded();
        Loan? existingLoan = _jsonData.Loans!.FirstOrDefault(l => l.Id == loan.Id);
        if (existingLoan != null)
        {
            existingLoan.BookItemId = loan.BookItemId;
            existingLoan.PatronId = loan.PatronId;
            existingLoan.LoanDate = loan.LoanDate;
            existingLoan.DueDate = loan.DueDate;
            existingLoan.ReturnDate = loan.ReturnDate;
            await _jsonData.SaveLoans(_jsonData.Loans!);
            await _jsonData.LoadData();
        }
    }

    ```

1. Pour accepter la méthode UpdateLoan mise à jour, sélectionnez **Accept**.

1. Enregistrez les changements apportés au fichier JsonLoanRepository.cs.

1. Générez votre solution afin de vérifier qu’il n’y a aucune erreur.

    Vous verrez des avertissements. Vous pouvez les ignorer pour le moment.

#### Tâche 3 : refactoriser les méthodes dans JsonPatronRepository de façon à utiliser LINQ

La classe JsonPatronRepository comprend les méthodes SearchPatrons, GetPatron et UpdatePatron, et c’est un excellent candidat pour l’optimisation. Vous allez refactoriser ces méthodes, en remplaçant les boucles foreach par LINQ pour améliorer la lisibilité et la maintenance du code.

Utilisez les étapes suivantes pour terminer cette section de l’exercice :

1. Ouvrez le fichier **JsonPatronRepository.cs**.

1. Sélectionnez la méthode **SearchPatrons**.

    La méthode SearchPatrons est conçue pour rechercher des usagers par nom.

    ```csharp

    public async Task<List<Patron>> SearchPatrons(string searchInput)
    {
        await _jsonData.EnsureDataLoaded();
        List<Patron> searchResults = new List<Patron>();
        foreach (Patron patron in _jsonData.Patrons)
        {
            if (patron.Name.Contains(searchInput))
            {
                searchResults.Add(patron);
            }
        }
        searchResults.Sort((p1, p2) => String.Compare(p1.Name, p2.Name));
        searchResults = _jsonData.GetPopulatedPatrons(searchResults);
        return searchResults;
    }

    ```

1. Ouvrez la conversation en ligne, puis entrez un prompt qui refactorise la méthode à l’aide de LINQ.

    Par exemple, entrez le prompt suivant :

    ```plaintext
    #selection refactor selection using LINQ with `_jsonData.Patrons!. Replace the loop with `Where`, `OrderBy`, and `GetPopulatedPatrons`.
    ```

1. Prenez une minute pour passer en revue la mise à jour suggérée.

    La mise à jour suggérée doit ressembler au code suivant :

    ```csharp

    public async Task<List<Patron>> SearchPatrons(string searchInput)
    {
        await _jsonData.EnsureDataLoaded();
        List<Patron> searchResults = _jsonData.Patrons!
            .Where(patron => patron.Name.Contains(searchInput))
            .OrderBy(patron => patron.Name)
            .ToList();
        searchResults = _jsonData.GetPopulatedPatrons(searchResults);
        return searchResults;
    }

    ```

1. Pour accepter la méthode SearchPatrons mise à jour, sélectionnez **Accept**.

1. Sélectionnez la méthode **GetPatron**.

    La méthode GetPatron est conçue pour retourner l’usager correspondant à l’ID spécifié.

    ```csharp

    public async Task<Patron?> GetPatron(int id)
    {
        await _jsonData.EnsureDataLoaded();
        foreach (Patron patron in _jsonData.Patrons!)
        {
            if (patron.Id == id)
            {
                Patron populated = _jsonData.GetPopulatedPatron(patron);
                return populated;
            }
        }
        return null;
    }

    ```

1. Ouvrez la conversation en ligne, puis entrez un prompt qui refactorise la méthode à l’aide de LINQ.

    Par exemple, entrez le prompt suivant :

    ```plaintext
    #selection refactor selection using LINQ with `_jsonData.Patrons!. Use `Where`, `Select` and `GetPopulatedPatron` to return `FirstOrDefault`
    ```

1. Prenez une minute pour passer en revue la mise à jour suggérée.

    La mise à jour suggérée doit ressembler au code suivant :

    ```csharp

    public async Task<Patron?> GetPatron(int id)
    {
        await _jsonData.EnsureDataLoaded();
        var patron = _jsonData.Patrons!
            .Where(p => p.Id == id)
            .Select(p => _jsonData.GetPopulatedPatron(p))
            .FirstOrDefault();
        return patron;
    }

    ```

    Ce code peut être simplifié davantage :

    ```C#

    public async Task<Patron?> GetPatron(int id)
    {
        await _jsonData.EnsureDataLoaded();
        return _jsonData.Patrons!
            .Where(p => p.Id == id)
            .Select(p => _jsonData.GetPopulatedPatron(p))
            .FirstOrDefault();
    }

    ```

1. Pour accepter la méthode GetPatron mise à jour, sélectionnez **Accept**.

1. Sélectionnez la méthode **UpdatePatron**.

    La méthode UpdatePatron est conçue pour mettre à jour l’usager avec l’ID spécifié.

    ```csharp

    public async Task UpdatePatron(Patron patron)
    {
        await _jsonData.EnsureDataLoaded();
        var patrons = _jsonData.Patrons!;
        Patron existingPatron = null;
        foreach (var p in patrons)
        {
            if (p.Id == patron.Id)
            {
                existingPatron = p;
                break;
            }
        }
        if (existingPatron != null)
        {
            existingPatron.Name = patron.Name;
            existingPatron.ImageName = patron.ImageName;
            existingPatron.MembershipStart = patron.MembershipStart;
            existingPatron.MembershipEnd = patron.MembershipEnd;
            existingPatron.Loans = patron.Loans;
            await _jsonData.SavePatrons(patrons);
            await _jsonData.LoadData();
        }
    }

    ```

1. Ouvrez la conversation en ligne, puis entrez un prompt qui refactorise la méthode à l’aide de LINQ.

    Par exemple, entrez le prompt suivant :

    ```plaintext
    #selection refactor selection using LINQ to find `patron` in `_jsonData.Patrons!. Replace existing patron with `patron`.
    ```

1. Prenez une minute pour passer en revue la mise à jour suggérée.

    La mise à jour suggérée doit ressembler au code suivant :

    ```csharp

    public async Task UpdatePatron(Patron patron)
    {
        await _jsonData.EnsureDataLoaded();
        var patrons = _jsonData.Patrons!;
        var existingPatron = patrons.FirstOrDefault(p => p.Id == patron.Id);
        if (existingPatron != null)
        {
            existingPatron.Name = patron.Name;
            existingPatron.ImageName = patron.ImageName;
            existingPatron.MembershipStart = patron.MembershipStart;
            existingPatron.MembershipEnd = patron.MembershipEnd;
            existingPatron.Loans = patron.Loans;
            await _jsonData.SavePatrons(patrons);
            await _jsonData.LoadData();
        }
    }

    ```

1. Pour accepter la méthode UpdatePatron mise à jour, sélectionnez **Accept**.

#### Tâche 4 : Vérifier votre travail

Pour vérifier votre travail, effectuez ces étapes :

1. Pour nettoyer la solution, cliquez avec le bouton droit sur **AccelerateAppDevGitHubCopilot**, puis sélectionnez **Clean**.

    Cette action supprime tous les artefacts de build de la build précédente. Le nettoyage de la solution réinitialise les fichiers de données JSON à leurs valeurs d’origine (dans le répertoire de sortie).

1. Générez l’application et vérifiez qu’aucune erreur n’est détectée.

1. Exécutez l'application.

    Vous pouvez exécuter l’application à partir de la vue Explorateur de solutions en cliquant avec le bouton droit sur le projet **Library.Console**, en sélectionnant **Déboguer**, puis en sélectionnant **Démarrer une nouvelle instance**.

1. Lorsque vous êtes invité à entrer un nom d’usager, tapez **One**, puis appuyez sur Entrée.

1. À l’invite « Matching Patrons », tapez **2**, puis appuyez sur Entrée.

1. À l’invite « Book Loans », tapez **1**, puis appuyez sur Entrée.

1. À l’invite « Input Options », tapez **r**, puis appuyez sur Entrée.

1. Vérifiez que le message **« Book was successfully returned. »** est affichée.

1. Pour commencer une nouvelle recherche, tapez **s**, puis appuyez sur Entrée.

1. Lorsque vous êtes invité à entrer un nom d’usager, tapez **One**, puis appuyez sur Entrée.

1. À l’invite « Matching Patrons », tapez **2**, puis appuyez sur Entrée.

1. Vérifiez que le premier prêt de livre est marqué **Returned: True**.

1. À l’invite « Input Options », tapez **q**, puis appuyez sur Entrée.

1. Arrêtez l’application.

#### Résumé - Exercice 9

Dans cet exercice, vous avez refactorisé les méthodes d’accès aux données dans les classes JsonData, JsonLoanRepository et JsonPatronRepository pour utiliser LINQ. Ces modifications peuvent améliorer la lisibilité, la facilité de maintenance et les performances du code.
