---
demo:
  title: "Démonstration\_: Créer du code à l’aide de complétions de ligne de code"
  module: 'Module 3: Develop code features using GitHub Copilot tools'
---

# Démonstration : Créer du code à l’aide de complétions de ligne de code

## Instructions

Les activités de la version de démonstration sont conçues pour un environnement qui inclut les ressources suivantes :

- Visual Studio Code.
- L’extension du kit de développement C# pour Visual Studio Code.
- Les extensions GitHub Copilot et GitHub Copilot Chat pour Visual Studio Code. Il est nécessaire de disposer d’un compte GitHub avec un abonnement actif pour GitHub Copilot.
- Des exemples de projets de code créés en C#.

**REMARQUE** : Nous recommandons aux instructeurs d’utiliser leur propre compte GitHub et leur abonnement GitHub Copilot pour les démonstrations. Ainsi vous pouvez contrôler et personnaliser votre environnement de développement. Cette démarche facilite également l’ajustement des démonstrations en fonction des besoins de vos salles de classe.

**IMPORTANT** : Si vous choisissez d’exécuter les démonstrations dans l’environnement de laboratoire hébergé plutôt que sur votre ordinateur personnel instructeur, vous pouvez décompresser les exemples d’applications dans l’environnement hébergé. Vous devez configurer les extensions GitHub Copilot dans l’environnement hébergé avant de pouvoir exécuter les démonstrations. Vous pouvez constater que l’environnement hébergé est plus lent que votre environnement local. Vous devrez probablement ajuster l’allure des démonstrations en conséquence.

### Présentez la version de démonstration

GitHub Copilot peut fournir des suggestions de complétion de code pour de nombreux langages de programmation et un large éventail d’infrastructures, mais fonctionne particulièrement bien pour Python, JavaScript, TypeScript, Ruby, Go, C# et C++. Les complétions de ligne de code sont générées en fonction du contexte du code que vous écrivez. Vous pouvez accepter, rejeter ou accepter partiellement les suggestions fournies par GitHub Copilot.

GitHub Copilot fournit deux façons de générer des complétions de ligne de code :

- **Depuis un commentaire** : Vous pouvez générer des complétions de ligne de code en écrivant un commentaire qui décrit le code que vous souhaitez générer. GitHub Copilot fournit des suggestions de complétion de code basées sur le commentaire que vous écrivez.

- **Depuis le code** : Vous pouvez générer des complétions de ligne de code en commençant une ligne de code ou en appuyant sur Entrée après une ligne de code terminée. GitHub Copilot fournit des suggestions de complétion de code basées sur le code que vous écrivez.

Dans cette version de démonstration, vous utilisez GitHub Copilot pour générer des complétions de ligne de code dans votre environnement Visual Studio Code.

### Créer une application console dans votre environnement Visual Studio Code

Dans cette version de démonstration, vous allez créer une application console à l’aide des outils GitHub Copilot.

Utilisez les étapes suivantes pour terminer cette section de la version de démonstration :

1. Ouvrez une nouvelle instance de Visual Studio Code, puis ouvrez l’affichage Conversation.

    Vous pouvez ouvrir la vue Conversation en sélectionnant **Ouvrir la conversation** dans le centre de commandes Visual Studio Code ou en utilisant le raccourci clavier **Ctrl+Alt+I**.

1. Dans l’affichage de Conversation, entrez l’invite suivante :

    ```plaintext
    @workspace /new console application named APL2007M3. Use C# LangVersion 12 and NET8.0. Only .cs and .csproj files. Enable ImplicitUsings and Nullable
    ```

1. Dans la vue Conversation, sélectionnez **Créer un espace de travail**.

    GitHub Copilot utilise votre invite pour créer l’espace de travail pour une nouvelle application de console. L’application utilise `C#` et `.NET8.0`. Le projet de code est nommé `APL2007M3` et inclut les fichiers `.cs` et `.csproj`. Le fichier `APL2007M3.csproj` spécifie C# `LangVersion 12` et active `ImplicitUsings` et `Nullable`.

1. Dans la boîte de dialogue Sélectionner un dossier, accédez à votre dossier Bureau, sélectionnez **Bureau**, puis sélectionnez **Sélectionner en tant que dossier parent**.

    Vous êtes invité à sélectionner un dossier parent pour le nouvel espace de travail. La sélection du dossier Bureau est un bon choix pour cette version de démonstration. Le dossier Bureau est facile à trouver. N’oubliez pas d’effectuer un nettoyage à la fin de cette formation.

1. Lorsque vous êtes invité à ouvrir le nouveau projet, sélectionnez **Ouvrir**.

1. Dans la vue Explorateur, sélectionnez **Program.cs**.

1. Remplacez le contenu du fichier Program.cs par le code suivant :

    ```csharp

    namespace ReportGenerator
    {
        class QuarterlyIncomeReport
        {
            static void Main(string[] args)
            {
                // create a new instance of the class
                QuarterlyIncomeReport report = new QuarterlyIncomeReport();
                // call the GenerateSalesData method
                // call the QuarterlySalesReport method
            }
            public void QuarterlySalesReport()
            {
                Console.WriteLine("Quarterly Sales Report");
            }
        }    
    }

    ```

Vos exigences de configuration sont complètes et vous êtes prêt à poursuivre la version de démonstration.

### Utiliser GitHub Copilot pour générer des complétions de ligne de code depuis un commentaire

GitHub Copilot génère des suggestions de complétion de code basées sur le commentaire et le contexte existant de votre application. Vous pouvez utiliser les commentaires pour décrire des extraits de code, des méthodes, des structures de données et d’autres éléments de code.

Utilisez les étapes suivantes pour terminer cette section de la version de démonstration :

1. Dans le fichier **Program.cs**, créez deux lignes de code vides sous la méthode `Main`.

1. Pour créer une structure de données qui peut être utilisée pour générer des données de test, créez le commentaire de code suivant, puis appuyez sur Entrée :

    ```C#
    // public struct SalesData. Include the following fields: date sold, department name, product ID, quantity sold, unit price
    ```

    GitHub Copilot génère une ou plusieurs suggestions de complétion de code en fonction de votre commentaire de code et de tout code existant qu’il trouve dans votre application.

1. Prenez un moment pour examiner les suggestions de complétion de code fournies par GitHub Copilot.

    > [!NOTE]
    > Si GitHub Copilot génère des suggestions pour une méthode plutôt qu’une structure de données, tapez **public str** et attendez que la suggestion de complétion du code soit mise à jour. GitHub Copilot utilise les informations supplémentaires pour améliorer ses suggestions.

    Remarquez les types de données utilisés pour déclarer les champs de la structure de données. GitHub Copilot sélectionne les types de données et les noms des variables en fonction de votre code existant et du commentaire de code. GitHub Copilot tente de déterminer comment l’application utilise des variables puis définit les types de données en conséquence.

    Lorsque GitHub Copilot génère plusieurs suggestions, vous pouvez parcourir les suggestions en sélectionnant les flèches gauche ou droite (`>` ou `<`) situées à gauche du bouton **Accepter**. Cela vous permet d’évaluer et de sélectionner la suggestion qui convient le mieux à vos besoins.

    Il est possible d’accepter une suggestion de complétion de code qui n’est pas une correspondance exacte pour ce que vous voulez. Les modifications requises pour « corriger » la suggestion doivent toutefois être claires. Dans ce cas, certains des types de données ne correspondent pas à votre besoin, mais vous pouvez les ajuster après avoir accepté la saisie automatique suggérée.

    Si aucune des options suggérées ne satisfait vos besoins, vous pouvez essayer deux choses. Pour ouvrir un nouvel onglet de l’éditeur contenant une liste d’autres suggestions, appuyez sur les touches **Ctrl** + **Entrer**. Cette combinaison de touches rapides ouvre un nouvel onglet contenant jusqu’à 10 suggestions supplémentaires. Chaque suggestion est suivie d’un bouton à utiliser pour accepter la suggestion. L’onglet se ferme automatiquement après l’acceptation d’une suggestion. Votre autre option consiste à appuyer sur la touche **Échap** pour ignorer les suggestions et réessayer. Vous pouvez ajuster le commentaire de code pour fournir davantage de contexte que GitHub Copilot peut utiliser.

    > [!NOTE]
    > GitHub Copilot peut parfois proposer une suggestion par étapes. Si cela se produit, vous pouvez appuyer sur Entrer pour afficher les étapes supplémentaires de la suggestion après l’appui sur la touche Tab.

1. Pour accepter une structure de données suggérée, appuyez sur la touche Tab ou sélectionnez **Accepter**.

1. Pour modifier les types de données de champ, mettez à jour votre code comme suit :

    ```csharp

    public struct SalesData
    {
        public DateOnly dateSold;
        public string departmentName;
        public int productID;
        public int quantitySold;
        public double unitPrice;
    }

    ```

    L’ajustement rapide des suggestions de complétion de code vous permet de vous assurer de la génération du code souhaité. Il est particulièrement important d’apporter des corrections au début de votre processus de développement, lorsque de grandes parties de votre codebase doivent encore être développées. Les saisies semi-automatiques de code suivantes sont basées sur le code déjà écrit. Il est donc important de veiller à ce que votre code soit aussi précis que possible.

1. Créez deux lignes de code vides sous la structure de données `SalesData`.

1. Pour créer une méthode qui génère des données de test en utilisant la structure de données `SalesData`, écrivez le commentaire de code suivant, puis appuyez sur Entrée :

    ```C#
    /* the GenerateSalesData method returns 1000 SalesData records. It assigns random values to each field of the data structure */
    ```

1. Prenez un moment pour examiner les suggestions de complétion de code fournies par GitHub Copilot.

    Remarquez que la méthode `GenerateSalesData` est conçue pour retourner un tableau d’objets `SalesData`. La méthode génère 1 000 enregistrements de données de test, avec des valeurs aléatoires affectées à chaque champ de la structure de données `SalesData`.

    Vous devez toujours évaluer les suggestions proposées par GitHub Copilot et GitHub Copilot Chat, même lorsqu’elles semblent correctes.

    > [!NOTE]
    > Si GitHub Copilot propose une seule ligne de code au lieu d’une méthode complète `GenerateSalesData`, appuyez sur **Ctrl+Entrée** pour ouvrir l’onglet Suggestions de GitHub Copilot. Passez en revue les suggestions dans le nouvel onglet. À l’étape suivante, utilisez le bouton « Accepter une suggestion # » pour accepter la suggestion. GitHub Copilot présente des suggestions incrémentielles à l’occasion. Bien que vous puissiez accepter les complétions de code de manière incrémentielle, il est préférable d’utiliser l’onglet Suggestions de GitHub Copilot pour évaluer les suggestions complètes avant de prendre une décision d’accepter ou d’ignorer.

1. Faites défiler les suggestions de saisie semi-automatique de code et sélectionnez celle qui correspond le mieux aux besoins.

1. Pour accepter la complétion de code, appuyez sur la touche Tab.

    Notez que la suggestion de complétion du code inclut une erreur de syntaxe dans le code utilisé pour générer le champ `DateSold`. `DateOnly` accepte trois valeurs entières à répertorier dans le bon ordre : **Année**, **Mois**, **Jour**.

1. Pour spécifier une année unique pour le code utilisé pour générer le champ `DateSold`, mettez à jour la ligne de code comme suit :

    ```C#
    salesData[i].DateSold = new DateOnly(2023, random.Next(1, 13), random.Next(1, 29));
    ```

1. Si nécessaire, ajustez les autres lignes de code pour qu’elles correspondent à l’extrait de code suivant :

    ```csharp

    public SalesData[] GenerateSalesData()
    {
        SalesData[] salesData = new SalesData[1000];
        Random random = new Random();
        for (int i = 0; i < salesData.Length; i++)
        {
            salesData[i].dateSold = new DateOnly(2023, random.Next(1, 13), random.Next(1, 29));
            salesData[i].departmentName = "Department " + random.Next(1, 11);
            salesData[i].productID = random.Next(1, 101);
            salesData[i].quantitySold = random.Next(1, 101);
            salesData[i].unitPrice = random.NextDouble() * 100;
        }
        return salesData;
    }

    ```

La possibilité de générer du code depuis des commentaires de code est une fonctionnalité puissante de GitHub Copilot. Avec seulement deux commentaires, vous avez pu générer une structure de données et une méthode qui génère des données de test.

### Utiliser GitHub Copilot pour générer des complétions de ligne de code

GitHub Copilot peut générer des complétions de ligne de code en fonction du code que vous entrez. Vous pouvez générer des complétions de ligne de code de deux façons :

- Commencez à entrer une ligne de code, puis attendez que GitHub Copilot suggère une autocomplétion pour votre ligne de code non terminée.
- Entrez une ligne de code complète, appuyez sur **Entrer**, puis attendez que GitHub Copilot suggère une saisie automatique pour la ligne de code.

> [!NOTE]
> GitHub Copilot génère les complétions de code suggérées en fonction du code que vous entrez et du contexte défini par le code au sein de votre application. Plus vous avez de code dans votre application, en supposant qu’il s’agit d’un code de bonne qualité, plus GitHub Copilot dispose de contexte. À mesure que le volume et la qualité du code existant augmentent, il en va de même de la qualité et de la fiabilité des complétions de ligne de code suggérés par GitHub Copilot. GitHub Copilot excelle pour générer des complétions de ligne de code pour les tâches et modèles de programmation courants, en particulier quand une séquence de composants connexes doit être générée.

Dans cette partie de la version de démonstration, vous travaillez sur la méthode `QuarterlySalesReport`.

Voici les tâches que vous devez effectuer :

- Mettre à jour le constructeur de méthode avec un paramètre qui accepte votre collection d’objets `SalesData`.
- Utiliser GitHub Copilot pour générer des complétions de ligne de code qui traitent les données de ventes pour le rapport trimestriel.
- Exécutez l’application et examinez le rapport sur le chiffre de ventes trimestrielles.

Utilisez les étapes suivantes pour terminer cette section de la version de démonstration :

1. Mettre à jour le constructeur de méthode pour `QuarterlySalesReport`, comme suit :

    ```C#
    public void QuarterlySalesReport(SalesData[] salesData)
    ```

1. Prenez un moment pour réfléchir au code que vous devez développer.

    Le concept est simple. Vous souhaitez que votre code calcule les ventes trimestrielles en fonction de vos données de ventes, puis écrive un rapport. Pour ce faire, votre code doit :

    - Itérez via la collection `salesData`.
    - Calculez la valeur de chaque vente en fonction de la quantité vendue et du prix unitaire.
    - Utilisez la date de vente pour déterminer le trimestre auquel appartient une vente.
    - Additionnez les ventes der chaque trimestre.
    - Écrivez un rapport sur les ventes par trimestre.

    Une option consiste à commencer à entrer le code d’une boucle `foreach`, puis à voir ce que GitHub Copilot suggère.

1. Dans la méthode `QuarterlySalesReport`, créez une ligne de code en haut du bloc de code.

    Il doit y avoir au moins une ligne de code vide entre la nouvelle ligne de code et celle contenant `Console.WriteLine()`.

1. Pour générer une complétion de ligne de code, tapez `foreach (` et attendez que GitHub Copilot suggère des options de complétion de ligne de code.

1. Examinez la complétion de code suggérée par GitHub Copilot.

    La complétion de code suggérée n’est pas ce que vous vouliez.

    Bien que GitHub Copilot suggère une boucle `foreach` qui itère dans les `salesData`, il n’y a aucune analyse ni aucun calcul à l’intérieur de la boucle. Chacun des options suggérées incluent des instructions `Console.WriteLine` que vous ne souhaitez pas ou dont vous n’avez pas besoin.

1. Prenez un moment pour réfléchir à la raison pour laquelle GitHub Copilot suggère des instructions `Console.WriteLine`.

    Rappelez-vous que GitHub Copilot génère des suggestions de complétion de code en fonction du contexte de votre code. Dans ce cas, vous n’avez pas vraiment beaucoup de code à prendre en compte par GitHub Copilot. Et la situation empire.

    Le code que GitHub Copilot voit dans votre méthode est une instruction `Console.WriteLine`. Sans aucun autre contexte disponible dans la méthode et aucune méthode semblable dans votre codebase à partir duquel dessiner, GitHub Copilot conclut que vous *souhaitez* peut-être des instructions `Console.WriteLine` dans la boucle `foreach`.

    GitHub Copilot fonctionne mieux lorsque votre code est propre et ciblé. Si vous voyez des commentaires de code superflus ou même des instructions dans votre code, vous pouvez les supprimer avant d’essayer d’utiliser les saisies semi-automatiques de code GitHub Copilot.

1. Pour nettoyer votre code avant de demander à GitHub Copilot de refaire un autre essai, procédez comme suit :

    - Annulez la complétion de code suggérée `foreach (`.
    - Supprimez l’instruction `foreach (` partielle que vous avez entrée.
    - Supprimez l’instruction `Console.WriteLine` de votre méthode `QuarterlySalesReport`.

    Vous devriez maintenant être prêt à réessayer GitHub Copilot.

1. Vérifiez que votre méthode `QuarterlySalesReport` ressemble au code suivant :

    ```C#
    public void QuarterlySalesReport(SalesData[] salesData)
    {


    }
    ```

1. Positionnez le curseur sur une ligne de code vide à l’intérieur de la méthode `QuarterlySalesReport`, puis appuyez sur Entrée.

    GitHub Copilot peut prendre un certain temps pour générer la complétion de code suggérée.

1. Prenez un moment pour examiner les complétions de code suggérées.

    > [!NOTE]
    > Bien que GitHub Copilot n’ait qu’un nom de méthode et un paramètre à utiliser, cela peut être suffisant pour générer des suggestions utiles. Vous devriez voir des suggestions qui calculent les ventes par trimestre. Rejeter les suggestions et réessayer peut fournir des résultats différents.

    Vous pouvez parcourir les suggestions en sélectionnant `>` ou `<`.

    Notez que la complétion de code suggérée effectue une itération dans les données de ventes et effectue des calculs trimestriels des ventes.

1. Pour accepter la complétion de code suggérée, appuyez sur la touche Tab.

    La complétion de code suggérée calcule et affiche le chiffre d’affaires trimestriel en fonction des données de ventes.

    ```csharp

    // create a dictionary to store the quarterly sales data
    Dictionary<string, double> quarterlySales = new Dictionary<string, double>();
    // iterate through the sales data
    foreach (SalesData data in salesData)
    {
        // calculate the total sales for each quarter
        string quarter = GetQuarter(data.dateSold.Month);
        double totalSales = data.quantitySold * data.unitPrice;
        if (quarterlySales.ContainsKey(quarter))
        {
            quarterlySales[quarter] += totalSales;
        }
        else
        {
            quarterlySales.Add(quarter, totalSales);
        }
    }
    // display the quarterly sales report
    Console.WriteLine("Quarterly Sales Report");
    Console.WriteLine("----------------------");
    foreach (KeyValuePair<string, double> quarter in quarterlySales)
    {
        Console.WriteLine(entry.Key + ": $" + entry.Value);
    }

    ```

1. Notez que la méthode `GetQuarter` est utilisée pour déterminer le trimestre en fonction du mois de la vente.

    Cette méthode n’est pas implémentée dans votre code, mais elle est requise pour la génération et l’exécution du code.

1. Créez deux lignes de code vide sous la méthode `QuarterlySalesReport`.

1. Notez que GitHub Copilot suggère une complétion de code pour la méthode `GetQuarter`.

    Avec le contexte fourni par la méthode `QuarterlySalesReport`, GitHub Copilot peut facilement générer une complétion de code pour la méthode `GetQuarter`, qui détermine le trimestre en fonction du mois de la vente.

1. Prenez un moment pour examiner la complétion de la ligne de code suggérée pour la méthode `GetQuarter`.

1. Pour accepter la complétion de code suggérée, appuyez sur la touche Tab.

    ```csharp

    public string GetQuarter(int month)
    {
        if (month >= 1 && month <= 3)
        {
            return "Q1";
        }
        else if (month >= 4 && month <= 6)
        {
            return "Q2";
        }
        else if (month >= 7 && month <= 9)
        {
            return "Q3";
        }
        else
        {
            return "Q4";
        }
    }

    ```

1. Notez que la méthode `Main` doit être terminée avant de pouvoir exécuter le code.

    Vous pouvez utiliser les commentaires de la méthode `Main` pour mettre à jour votre code.

1. Positionnez le curseur à la fin du commentaire de code `// call the GenerateSalesData method`, puis appuyez sur Entrée.

    GitHub Copilot utilise le commentaire pour proposer une instruction appelante pour la méthode.

1. Examinez, puis acceptez la complétion de code suggérée par GitHub Copilot.

1. Répétez le processus pour le commentaire de code `// call the QuarterlySalesReport method`.

1. Votre méthode `Main` doit contenir le code suivant :

    ```csharp

    static void Main(string[] args)
    {
        // create a new instance of the class
        QuarterlyIncomeReport report = new QuarterlyIncomeReport();
        // call the GenerateSalesData method
        SalesData[] salesData = report.GenerateSalesData();
        // call the QuarterlySalesReport method
        report.QuarterlySalesReport(salesData);
    }

    ```

1. Prenez un moment pour examiner le code de votre classe `QuarterlyIncomeReport`.

    ```csharp

    namespace ReportGenerator
    {
        class QuarterlyIncomeReport
        {
            static void Main(string[] args)
            {
                // create a new instance of the class
                QuarterlyIncomeReport report = new QuarterlyIncomeReport();
                // call the GenerateSalesData method
                SalesData[] salesData = report.GenerateSalesData();
                // call the QuarterlySalesReport method
                report.QuarterlySalesReport(salesData);
            }
            /* public struct SalesData includes the following fields: date sold, department name, product ID, quantity sold, unit price */
            public struct SalesData
            {
                public DateOnly dateSold;
                public string departmentName;
                public int productID;
                public int quantitySold;
                public double unitPrice;
            }
            /* the GenerateSalesData method returns 1000 SalesData records. It assigns random values to each field of the data structure */
            public SalesData[] GenerateSalesData()
            {
                SalesData[] salesData = new SalesData[1000];
                Random random = new Random();
                for (int i = 0; i < 1000; i++)
                {
                    salesData[i].dateSold = new DateOnly(2023, random.Next(1, 13), random.Next(1, 29));
                    salesData[i].departmentName = "Department " + random.Next(1, 11);
                    salesData[i].productID = random.Next(1, 101);
                    salesData[i].quantitySold = random.Next(1, 101);
                    salesData[i].unitPrice = random.NextDouble() * 100;
                }
                return salesData;
            }
            public void QuarterlySalesReport(SalesData[] salesData)
            {
                // create a dictionary to store the quarterly sales data
                Dictionary<string, double> quarterlySales = new Dictionary<string, double>();
                // iterate through the sales data
                foreach (SalesData data in salesData)
                {
                    // calculate the total sales for each quarter
                    string quarter = GetQuarter(data.dateSold.Month);
                    double totalSales = data.quantitySold * data.unitPrice;
                    if (quarterlySales.ContainsKey(quarter))
                    {
                        quarterlySales[quarter] += totalSales;
                    }
                    else
                    {
                        quarterlySales.Add(quarter, totalSales);
                    }
                }
                // display the quarterly sales report
                Console.WriteLine("Quarterly Sales Report");
                Console.WriteLine("----------------------");
                foreach (KeyValuePair<string, double> quarter in quarterlySales)
                {
                    Console.WriteLine(entry.Key + ": $" + entry.Value);
                }
            }
            public string GetQuarter(int month)
            {
                if (month >= 1 && month <= 3)
                {
                    return "Q1";
                }
                else if (month >= 4 && month <= 6)
                {
                    return "Q2";
                }
                else if (month >= 7 && month <= 9)
                {
                    return "Q3";
                }
                else
                {
                    return "Q4";
                }
            }
        }
    }
    
    ```

    Ce code a été créé presque entièrement à l’aide des saisies semi-automatiques de lignes de code générées par GitHub Copilot. Or, il est important que vous examiniez les suggestions de code, car des corrections peuvent être nécessaires, comme dans le cas présent. Vous devez toujours passer en revue les saisies semi-automatiques de code suggérées par GitHub Copilot pour vérifier que le code répond à vos besoins.

1. Pour examiner la sortie du rapport, exécutez l’application.

    Ouvrez une fenêtre du Terminal dans Visual Studio Code, puis entrez la commande suivante :

    ```bash
    dotnet run
    ```

    La sortie devrait afficher le rapport de chiffre d’affaires trimestriel, en indiquant le nom du service, le trimestre et le chiffre d’affaires pour chaque service et trimestre représenté dans les données de test.

1. Examinez la sortie dans la fenêtre du Terminal.

    Même si les résultats trimestriels sont basés sur des valeurs numériques aléatoires, vous devez obtenir un rapport dont la mise en forme est semblable à la sortie suivante :

    ```output

    Quarterly Sales Report
    ----------------------
    Q3: $635637.5019563352
    Q4: $672247.315297204
    Q2: $667269.194630603
    Q1: $642769.2700531208

    ```

    Il reste encore du travail à effectuer pour terminer la classe `QuarterlyIncomeReport`. Dans l’unité suivante, vous utilisez GitHub Copilot Chat pour étendre et mettre à jour votre application.

### Résumé

Dans cette version de démonstration, vous avez utilisé GitHub Copilot pour générer des complétions de ligne de code dans votre environnement Visual Studio Code. Vous avez utilisé des commentaires de code pour générer une structure de données et une méthode qui génère des données de test. Vous avez également utilisé des complétions de ligne de code pour générer le code qui traite les données de ventes pour un rapport de chiffre d’affaires trimestriel.
