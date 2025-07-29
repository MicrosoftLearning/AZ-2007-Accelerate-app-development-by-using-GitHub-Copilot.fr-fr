---
demo:
  title: "Démonstration\_: Créer du code à l’aide de GitHub Copilot Inline Chat"
  module: 'Module 3: Develop code features using GitHub Copilot tools'
---

# Démonstration : Créer du code à l’aide de GitHub Copilot Inline Chat

## Instructions

Les activités de la version de démonstration sont conçues pour un environnement qui inclut les ressources suivantes :

- Visual Studio Code.
- L’extension du kit de développement C# pour Visual Studio Code.
- Les extensions GitHub Copilot et GitHub Copilot Chat pour Visual Studio Code. Il est nécessaire de disposer d’un compte GitHub avec un abonnement actif pour GitHub Copilot.
- Des exemples de projets de code créés en C#.

**REMARQUE** : Nous recommandons aux instructeurs d’utiliser leur propre compte GitHub et leur abonnement GitHub Copilot pour les démonstrations. Ainsi vous pouvez contrôler et personnaliser votre environnement de développement. Cette démarche facilite également l’ajustement des démonstrations en fonction des besoins de vos salles de classe.

**IMPORTANT** : Si vous choisissez d’exécuter les démonstrations dans l’environnement de laboratoire hébergé plutôt que sur votre ordinateur personnel instructeur, vous pouvez décompresser les exemples d’applications dans l’environnement hébergé. Vous devez configurer les extensions GitHub Copilot dans l’environnement hébergé avant de pouvoir exécuter les démonstrations. Vous pouvez constater que l’environnement hébergé est plus lent que votre environnement local. Vous devrez probablement ajuster l’allure des démonstrations en conséquence.

### Présentez la version de démonstration

L’extension GitHub Copilot Chat pour Visual Studio Code comprend trois interfaces de conversation :

- La **vue Conversation** fournit un assistant IA disponible pour vous aider à tout moment.
- Une fenêtre de **Conversation rapide** peut être utilisée pour poser une question rapide, puis revenir à ce que vous faites.
- L’interface de **conversation incluse** s’ouvre directement dans l’éditeur pour les interactions contextuelles en cours de codage.

Les fenêtres Conversation et Conversation rapide activent des conversations interactives à plusieurs tours avec l’IA. Ces deux interfaces permettent de poser des questions, d’obtenir de l’aide sur un problème de codage et de générer du code. Pendant une conversation, les réponses GitHub Copilot comprennent du texte en langage naturel, des blocs de code et d’autres éléments. Lorsque des blocs de code sont fournis dans une réponse, vous pouvez les copier ou les injecter directement dans votre éditeur de code.

L’interface de conversation incluse est conçue pour fournir une aide contextuelle et des suggestions de code pendant que vous codez.

Dans cette version de démonstration, vous utilisez la fonctionnalité de conversation inline de GitHub Copilot pour générer de nouvelles fonctionnalités de code. La version de démonstration s’inscrit dans la continuité du scénario de projet présenté dans la version de démonstration précédente. Utilisez l’application exemple préparée, `APL2007M3SalesReport-InlineChat`, pour démarrer la version de démonstration. Au cours de cette version de démonstration, vous mettrez à jour la structure de données `SalesData` ainsi que la méthode `GenerateSalesData`. Vous allez également mettre à jour la méthode `QuarterlySalesReport` pour inclure des calculs supplémentaires et des options d’affichage.

#### Examinez les tâches de codage et les objectifs du projet

Cette version de démonstration se concentre sur l’utilisation de GitHub Copilot pour accélérer les tâches suivantes :

1. Vous mettrez à jour la structure de données `SalesData` et la méthode `GenerateSalesData` afin de produire un échantillon de données proche de données « réelles ».

    - dateSold : aucune modification n’est requise.
    - departmentName : Les valeurs de chaîne doivent être sélectionnées de manière aléatoire dans une liste de 8 services. Pour chaque nom de service, créez une abréviation de 4 caractères qui peut être incluse dans le productID.
    - productID : passer du type de données `int` au type `string`. Les valeurs de productID doivent être mises en forme à l’aide du modèle «`DDDD-###-SS-CC-MMM`», où les composants de l’ID sont définis comme suit :

        - code à 4 caractères représentant le service.
        - nombre à 3 chiffres représentant le produit.
        - code de 2 caractères représentant la taille du produit.
        - code à 2 caractères représentant la couleur du produit.
        - code à 3 caractères représentant le site de fabrication (sélectionné de façon aléatoire dans une liste de 10 sites de fabrication). Les codes doivent être un code de pays ISO à 2 lettres suivi d’un chiffre (par exemple, US1, CA2, MX3, etc.).

    - quantitySold : aucune modification n’est requise.
    - unitPrice : Augmentez la limite inférieure de la plage de prix à 25 et sa limite supérieure à 300.
    - baseCost : Ajoutez un champ pour le coût de fabrication de l’article. Les valeurs de baseCost doivent être générées à l’aide d’une remise générée aléatoirement sur l’unitPrice (5 à 20 %).
    - volumeDiscount : Ajoutez un champ pour un pourcentage de remise par volume. La valeur affectée à volumeDiscount doit être le composant entier de 10 % de la quantitySold (10 % de 19 unités = 1 % volumeDiscount).
    - Augmentez le nombre d’enregistrements générés à 10 000.

1. Vous allez mettre à jour la méthode `QuarterlySalesReport` comme suit :

    1. Lorsque vous affichez les résultats des ventes, listez les résultats dans un ordre logique. Par exemple, lorsque vous listez les ventes totales par trimestre, les trimestres doivent être listés dans l’ordre Q1 à Q4.
    1. Affichez les valeurs monétaires en utilisant les paramètres régionaux.
    1. Inclure les calculs du bénéfice et du pourcentage de bénéfice trimestriel
    1. Incluez les calculs des ventes, du bénéfice et du pourcentage de bénéfice trimestriels, par service.

#### Expliquer votre approche du développement d’invites pour GitHub Copilot Chat

La fonctionnalité de conversation inlined de GitHub Copilot utilise l’invite que vous envoyez pour comprendre la tâche ou le problème que vous essayez de résoudre. Les invites doivent être spécifiques et concises. De bonnes invites produisent de meilleures réponses.

Lorsque vous développez des invites pour GitHub Copilot, tenez compte des meilleures pratiques suivantes :

- Soyez spécifique et restez simple : Fournissez des invites claires et concises qui décrivent la tâche ou le problème à résoudre. Évitez d’utiliser un langage ou un jargon complexe qui peut induire en erreur l’IA.
- Utilisez le langage naturel : Écrivez les invites dans un ton conversationnel. Utilisez le langage naturel que vous utiliseriez dans une conversation avec un collègue ou un membre de l’équipe.
- Fractionnez des tâches complexes : Si la tâche est complexe, décomposez-la en étapes plus petites. Fournissez des invites pour chaque étape pour aider GitHub Copilot à générer le code approprié.
- Fournissez le contexte : Incluez des informations pertinentes pour aider GitHub Copilot à comprendre la tâche ou le problème à résoudre. Incluez des détails pertinents sur les données, les variables ou les blocs de code pour l’invite.
- Utilisez des participants à la conversation, des commandes slash et des variables de conversation : La fonctionnalité de conversation inlined de GitHub Copilot prend en charge les participants à la conversation, les commandes slash et les variables de conversation. Utilisez ces fonctionnalités pour interagir avec GitHub Copilot et pour fournir un contexte supplémentaire pour vos invites.

### Générer des structures de données à l’aide de la conversation incluse

Les projets commencent généralement par des fonctionnalités ou des paramètres qui sont fixes ou connus. La sélection d’une source de données ou la création d’un exemple de données est souvent un bon point de départ.

Dans cette section de la version de démonstration, vous utilisez des structures de données pour vous aider à créer des données de ventes simulées. Les données fournissent un contexte utile à GitHub Copilot lorsque vous mettez à jour la méthode `QuarterlySalesReport`.

> [!NOTE]
> Dans un projet d’entreprise réel, vous utiliseriez probablement des données historiques plutôt que de générer des données simulées. Dans cette formation, générer des données simulées permet de s’entraîner à utiliser les outils GitHub Copilot. Simuler des données n’est pas une pratique recommandée pour les projets d’entreprise.

Vos objectifs de projet indiquent que vous devez travailler sur les structures de données suivantes :

- Vous avez besoin d’une liste de 8 noms de service. Chaque nom de service doit être abrégé sous la forme d’une chaîne de 4 caractères. Choisissez un secteur d’activité pour votre société fictive, comme Vêtements ou Équipement sportif, puis demandez à GitHub Copilot de générer un dictionnaire des noms de service et des codes à 4 caractères.
- Vous avez besoin d’une liste de 10 sites de fabrication. Chaque site doit être représenté par un code à 3 caractères. Les codes peuvent être un code de pays ISO à 2 lettres suivi d’un chiffre (par exemple, US1, CA2, MX3, etc.). Demandez à GitHub Copilot de générer un dictionnaire des 10 sites de fabrication en utilisant 3 ou 4 codes de pays.
- Vous devez mettre à jour la structure de données `SalesData`. Vous devez inclure de nouveaux champs pour : code de service, code de site de fabrication. Vous devez également modifier le type de données pour productID, de `int` à `string`.

Pour créer et mettre à jour la structure de données, procédez comme suit :

1. Ouvrez le dossier de projet **APL2007M3SalesReport-InlineChat** dans Visual Studio Code.

1. Assurez-vous que l’application s’exécute et produit un rapport semblable à la sortie suivante :

    ```plaintext
    Quarterly Sales Report
    ----------------------
    Q3: $690095.7142725277
    Q4: $600536.3320750712
    Q2: $678194.7943550209
    Q1: $595963.0477790226
    ```

    Les données étant générées de façon aléatoire, les valeurs numériques varient selon chaque exécution.

1. Ouvrez le fichier Program.cs.

1. Positionnez le curseur sur une ligne vide sous la structure de données `SalesData`.

1. Pour ouvrir l’interface de conversation inline, appuyez sur **Ctrl+I** sur le clavier.

1. Entrez l’invite suivante :

    ```output
    I need a public struct ProdDepartments that contains a static string array for 8 clothing industry departments. Create separate string array containing 4-character abbreviations for each department name. The abbreviation must be unique. The department names should represent real department names for the clothing industry.
    ```

    Si vous avez une liste spécifique de noms de champ, vous pouvez les fournir dans l’invite. Par exemple, des données d’entreprise réelles peuvent être utilisées pour spécifier les noms de services.

1. Examinez les suggestions fournies par GitHub Copilot.

    Tant que l’invite est claire et spécifique, GitHub Copilot doit fournir une suggestion utile. Si la suggestion n’est pas conforme à vos attentes, vous pouvez la rejeter et réessayer. Dans ce cas, les noms des services ne sont pas importants. Vous pouvez donc accepter la suggestion.

    Votre structure de données doit ressembler au code suivant :

    ```csharp

    public struct ProdDepartments
    {
        public static string[] DepartmentNames =  ["Men's Clothing", "Women's Clothing", "Children's Clothing", "Accessories", "Footwear", "Outerwear", "Sportswear", "Undergarments"];
        public static string[] DepartmentAbbreviations =  ["MENS", "WOMN", "CHLD", "ACCS", "FOOT", "OUTR", "SPRT", "UNDR" ];
    }

    ```

1. Pour accepter la suggestion, appuyez sur la touche Tab ou sélectionnez **Accepter**.

    Vous pouvez également utiliser la fonctionnalité de conversation incluse pour documenter le nouveau code. Sélectionnez le code, appuyez sur **Ctrl+I** pour ouvrir la conversation incluse, entrez `/doc`, examinez la documentation incluse suggérée, puis acceptez la mise à jour.

1. Positionnez le curseur sur une ligne vide sous la structure de données `ProdDepartments`.

1. Pour ouvrir l’interface de conversation inline, appuyez sur **Ctrl+I** sur le clavier.

1. Entrez l’invite suivante :

    ```output
    I need a public struct ManufacturingSites that contains a static string array for 10 manSites. Manufacturing sites should be represented by a 3-character code that includes a 2-letter ISO country code followed by a digit. Use 3 ISO country codes.
    ```

    Si vous avez une liste spécifique de noms de champ, vous pouvez les fournir dans l’invite. Par exemple, des données d’entreprise réelles peuvent être utilisées pour spécifier les noms de champ.

1. Examinez les suggestions fournies par GitHub Copilot.

    Vos structures de données doivent ressembler au code suivant :

    ```csharp

    public struct ManufacturingSites
    {
        public static string[] manSites = [ "US1", "US2", "US3", "UK1", "UK2", "UK3", "JP1", "JP2", "JP3", "MX1" ];
    }

    ```

1. Pour accepter la suggestion, appuyez sur la touche Tab ou sélectionnez **Accepter**.

1. Sélectionnez la structure de données `SalesData`, puis appuyez sur **Ctrl+I** pour ouvrir l’interface de conversation incluse.

    Vous devez ajouter des champs pour `baseCost` et `volumeDiscount` à la structure de données `SalesData` (un `double` et un `int`). Vous devez également modifier le type de données de `productID`, de `int` à `string`.

1. Entrez l’invite suivante :

    ```output
    add double field baseCost and int field volumeDiscount to SalesData. Change productID from int to string.
    ```

    Dans la pratique, il peut être plus facile d’apporter ces modifications manuellement. Toutefois, l’utilisation de GitHub Copilot peut vous aider à apprendre comment structurer vos invites pour obtenir de meilleurs résultats.

1. Examinez les suggestions fournies par GitHub Copilot, puis sélectionnez **Accepter**.

    Vos structures de données SalesData mises à jour doivent ressembler au code suivant :

    ```csharp

    public struct SalesData
    {
        public DateOnly dateSold;
        public string departmentName;
        public string productID;
        public int quantitySold;
        public double unitPrice;
        public double baseCost;
        public int volumeDiscount;
    }

    ```

Les structures de données nouvelles ou mises à jour étant en place, vous pouvez maintenant travailler sur la mise à jour de la méthode `GenerateSalesData`.

### Mettre à jour la méthode GenerateSalesData en utilisant la conversation incluse

Vos objectifs de projet indiquent que vous devez mettre à jour la méthode `GenerateSalesData` pour qu’elle produise un exemple de données qui ressemble à des données « réelles ». Vous avez déjà mis à jour la structure de données `SalesData` pour qu’elle inclue de nouveaux champs pour le code de service et le code de site de fabrication. Vous avez également modifié le type de données de `productID`, de `int` à `string`. Vous devez maintenant mettre à jour la méthode `GenerateSalesData` pour qu’elle génère des données pour les champs mis à jour.

Vous devez implémenter les mises à jour suivantes :

- departmentName : Mettez à jour la valeur affectée. Attribuez un nom de service sélectionné de façon aléatoire depuis la structure de données `ProdDepartments`.
- productID : Mettez à jour la valeur affectée. Mettez en forme le productID à l’aide du modèle «`DDDD-###-SS-CC-MMM`» où les composants de l’ID sont définis comme suit :

    - code à 4 caractères représentant le service. Utilisez l’abréviation provenant de la structure de données `ProdDepartments` correspondant au nom du service affecté.
    - nombre à 3 chiffres représentant le produit. Le premier chiffre doit être le numéro d’index du service sélectionné de manière aléatoire. Les deux chiffres suivants doivent être un nombre aléatoire compris entre 1 et 99, mais inclure les premiers 0. Par exemple, 1 doit être mis en forme comme 01.
    - code à 2 caractères représentant la taille du produit. Sélectionnez de façon aléatoire une taille de produit dans une liste de 5 tailles : XS, S, M, L, XL.
    - code à 2 caractères représentant la couleur du produit. Sélectionnez de façon aléatoire une couleur de produit dans une liste de 8 abréviations de couleur à 2 caractères : BK, BL, GR, RD, YL, OR, WT, GY.
    - code à 3 caractères représentant le site de fabrication. Sélectionnez de façon aléatoire un site de fabrication dans la structure de données `ManufacturingSites`.

- unitPrice : Augmentez la limite inférieure de la plage de prix à 25 et sa limite supérieure à 300. Supposez que la taille et la couleur n’affectent pas le prix unitaire.
- baseCost : Affectez une valeur à baseCost qui représente les coûts de fabrication. Les valeurs peuvent être générées en utilisant une remise générée aléatoirement sur l’unitPrice (5 à 20 %). Pas réaliste, mais acceptable pour cette version de démonstration.
- volumeDiscount : Affectez une valeur à volumeDiscount qui représente une remise en pourcentage attribuée à l’acheteur au détail. La valeur affectée à volumeDiscount doit être le composant entier de 10 % de la quantitySold (10 % de 19 unités = 1 % volumeDiscount).

Pour mettre à jour la méthode `GenerateSalesData`, procédez comme suit :

1. Localisez la méthode `GenerateSalesData` dans le fichier Program.cs.

1. Sélectionnez la ligne de code utilisée pour affecter la valeur `departmentName`.

1. Pour ouvrir l’interface de conversation inline, appuyez sur **Ctrl+I** sur le clavier.

1. Entrez l’invite suivante :

    ```output
    Update the departmentName assignment to randomly select a department name. Use the ProdDepartments data structure. 
    ```

1. Examinez les suggestions fournies par GitHub Copilot, puis sélectionnez **Accepter**.

1. Créez trois lignes de code vides après l’affectation `departmentName`.

1. Prenez un moment pour réfléchir à la façon dont vous souhaitez construire la valeur affectée à `productID`.

    Les valeurs productID doivent être mises en forme comme «`DDDD-###-SS-CC-MMM`», où les composants de l’ID sont définis comme suit :

    - `DDDD` est un code à 4 caractères représentant le service. Utilisez l’abréviation provenant de la structure de données `ProdDepartments` correspondant au nom du service affecté.
    - `###` est une suite de 3 caractères numériques représentant un produit. Le premier chiffre est le numéro d’index du service. Vient après un nombre aléatoire de 1 à 99, avec un 0 de début (par exemple : « 07 »).
    - `SS` est un code à 2 caractères représentant la taille du produit. Sélectionnez de façon aléatoire une taille de produit dans une liste de 5 tailles : XS, S, M, L, XL.
    - `CC` est un code à 2 caractères représentant la couleur du produit. Sélectionnez de façon aléatoire une couleur de produit dans une liste de 8 abréviations de couleur à 2 caractères : BK, BL, GR, RD, YL, OR, WT, GY.
    - `MMM` est un code à 3 caractères représentant le site de fabrication. Sélectionnez de façon aléatoire un site de fabrication dans la structure de données `ManufacturingSites`.

    Cette spécification de mise en forme est trop complexe à décrire pour une seule invite. Elle doit être divisée en étapes plus petites.

    Il est important de noter que le numéro d’index du departmentName sélectionné peut être utilisé pour sélectionner la departmentAbbreviation et calculer le premier chiffre du numéro du produit.

1. Copiez les déclarations de variables suivantes et collez-les à l’emplacement de la seconde ligne de code vide créée.

    ```csharp

    int indexOfDept = 0;
    string deptAbb = "";
    string firstDigit = "";
    string nextTwoDigits = "";
    string sizeCode = "";
    string colorCode = "";
    string manufacturingSite = "";

    ```

    Vous devez disposer d’une ligne de code vide avant et après les déclarations de variables.

    Les déclarations de variables ne sont pas requises pour que la conversation inline génère des suggestions de mise à jour de code à partir d’une requête, mais elles permettent d’ancrer GitHub Copilot à une ligne de code spécifique à laquelle appartient la mise à jour.

1. Sélectionnez la ligne de code `int indexOfDept = 0;`, ouvrez la conversation incluse, puis entrez l’invite suivante :

    ```output
    Assign the array index for departmentName to indexOfDept.
    ```

1. Examinez les suggestions fournies par GitHub Copilot.

    Vous devriez voir une suggestion qui affecte le numéro d’index de tableau correspondant au departmentName sélectionné à indexOfDept.

    Si vous n’obtenez pas la suggestion attendue, vous pouvez sélectionner **Ignorer** pour rejeter la suggestion et réessayer. L’invite suivante fournit un contexte supplémentaire pour l’affectation :

    ```output
    Create an int named indexOfDept. Assign the array index number corresponding to the selected departmentName to indexOfDept.
    ```

    Cette invite spécifie la création d’une variable entière nommée `indexOfDept` ainsi que la façon d’affecter une valeur. Vous pouvez exécuter cette invite sans créer ou sélectionner la déclaration de variable, mais GitHub Copilot peut parfois perdre son point d’ancrage lorsque vous ouvrez la conversation incluse sans code sélectionné.

    > [!NOTE]
    > Vous pouvez utiliser le bouton **Activer/désactiver l’option Changer** (accessible à partir du menu déroulant **Autres actions** à droite des boutons **Accepter** et **Ignorer**) pour afficher/masquer le code supprimé par la mise à jour suggérée. Cela peut être utile lorsque vous souhaitez afficher le code d’origine et la mise à jour du code suggéré.

1. Pour accepter la suggestion fournie par GitHub Copilot, sélectionnez **Accepter**.

1. Sélectionnez la ligne de code `string deptAbb = "";`, ouvrez la conversation incluse, puis entrez l’invite suivante :

    ```output
    Use indexOfDept to assign a department abbreviation to deptAbb.
    ```

1. Examinez les suggestions fournies par GitHub Copilot.

    Vous devriez voir une suggestion qui affecte le numéro d’index de tableau correspondant au departmentName sélectionné à indexOfDept.

1. Pour accepter la suggestion fournie par GitHub Copilot, sélectionnez **Accepter**.

1. Sélectionnez la ligne de code `string firstDigit = "";`, ouvrez la conversation incluse, puis entrez l’invite suivante :

    ```output
    Assign indexOfDept + 1 to firstDigit.
    ```

1. Examinez les suggestions fournies par GitHub Copilot, puis sélectionnez **Accepter**.

1. Sélectionnez la ligne de code `string string nextTwoDigits = ""; = "";`, ouvrez la conversation incluse, puis entrez l’invite suivante :

    ```output
    Assign a random number 1-99 to nextTwoDigits. Include a leading 0 for numbers less than 10.
    ```

1. Examinez les suggestions fournies par GitHub Copilot, puis sélectionnez **Accepter**.

1. Sélectionnez la ligne de code `string sizeCode = "";`, ouvrez la conversation incluse, puis entrez l’invite suivante :

    ```output
    From the list {XS, S, M, L, XL}, randomly select a product size and assign it to sizeCode.
    ```

1. Examinez les suggestions fournies par GitHub Copilot, puis sélectionnez **Accepter**.

    Dans ce cas, vous devez voir une suggestion qui affecte une taille de produit sélectionnée de manière aléatoire à la variable `sizeCode`. GitHub Copilot peut suggérer d’utiliser une ou plusieurs lignes de code pour répondre à cette requête. De toute façon, il suggérera probablement de créer un tableau de chaînes des tailles de produit, puis d’utiliser `random` pour affecter l’une des tailles à `sizeCode`.

1. Sélectionnez la ligne de code `string colorCode = "";`, ouvrez la conversation incluse, puis entrez l’invite suivante :

    ```output
    From the list {BK, BL, GR, RD, YL, OR, WT, GY}, randomly select a product color and assign it to colorCode.
    ```

1. Examinez les suggestions fournies par GitHub Copilot, puis sélectionnez **Accepter**.

1. Sélectionnez la ligne de code `string manufacturingSite = "";`, ouvrez la conversation incluse, puis entrez l’invite suivante :

    ```output
    Assign a randomly selected manufacturing site to manufacturingSite.
    ```

1. Examinez les suggestions fournies par GitHub Copilot, puis sélectionnez **Accepter**.

1. Prenez quelques instants pour passer en revue votre code.

    Vous devez avoir une série de lignes de code qui attribuent des valeurs aux variables utilisées pour construire le productID. L’étape suivante consiste à construire la valeur productID.

    ```csharp

    int indexOfDept = Array.IndexOf(ProdDepartments.departmentNames, salesData[i].departmentName);
    string deptAbb = ProdDepartments.departmentAbbreviations[indexOfDept];
    string firstDigit = (indexOfDept + 1).ToString();
    string nextTwoDigits = random.Next(1, 100).ToString("D2");
    string sizeCode = new string[] { "XS", "S", "M", "L", "XL" }[random.Next(0, 5)];
    string colorCode = new string[] { "BK", "BL", "GR", "RD", "YL", "OR", "WT", "GY" }[random.Next(0, 8)];
    string manufacturingSite = ManufacturingSites.manufacturingSites[random.Next(0, ManufacturingSites.manufacturingSites.Length)];

    ```

1. Sélectionnez la ligne de code `salesData[i].productID = random.Next(1, 101);`, ouvrez la conversation incluse, puis entrez l’invite suivante :

    ```output
    Add a "-" to deptAbb, nextTwoDigits, sizeCode, and colorCode. Combine deptAbb, firstDigit, nextTwoDigits, sizeCode, colorCode, and manufacturingSite to create the productID.
    ```

1. Examinez les suggestions fournies par GitHub Copilot, puis sélectionnez **Accepter**.

    Vous devriez voir une suggestion qui construit la valeur productID à l’aide des variables que vous avez affectées précédemment. La suggestion doit inclure le code nécessaire pour mettre en forme le productID en tant que «`DDDD-###-SS-CC-MMM`».

1. Mettez à jour manuellement l’affectation `unitPrice` pour utiliser une plage de 25 à 300, comme suit :

    ```csharp
    salesData[i].unitPrice = random.Next(25, 300) + random.NextDouble();
    ```

1. Créez une ligne vide après l’affectation `unitPrice`.

1. Acceptez la complétion de la ligne de code qui s’affiche :

    GitHub Copilot doit fournir une suggestion qui affecte une valeur au `baseCost` qui ressemble à la ligne de code suivante :

    ```csharp
    salesData[i].baseCost = random.Next(10, 100) + random.NextDouble();
    ```

1. Sélectionnez la ligne de code utilisée pour attribuer une valeur à `salesData[i].baseCost`, ouvrez la conversation inlined, puis entrez l’invite suivante :

    ```output
    Discount the unitPrice by a random percentage between 5 and 20. Assign the result to baseCost.
    ```

1. Examinez les suggestions fournies par GitHub Copilot, puis sélectionnez **Accepter**.

1. Créez une ligne vide après l’affectation `baseCost` et acceptez la complétion de la ligne de code qui s’affiche.

    GitHub Copilot doit fournir une suggestion qui affecte une valeur à `volumeDiscount`.

1. Sélectionnez la ligne de code utilisée pour attribuer une valeur à `salesData[i].volumeDiscount`, ouvrez la conversation inlined, puis entrez l’invite suivante :

    ```output
    Assign 10 percent of quantitySold to volumeDiscount. Truncate any fractional values.
    ```

1. Examinez les suggestions fournies par GitHub Copilot, puis sélectionnez **Accepter**.

1. Votre méthode GenerateSalesData mise à jour doit maintenant ressembler à l’extrait de code suivant :

    ```csharp

    public SalesData[] GenerateSalesData()
    {
        SalesData[] salesData = new SalesData[1000];
        Random random = new Random();
        for (int i = 0; i < 1000; i++)
        {
            salesData[i].dateSold = new DateOnly(2023, random.Next(1, 13), random.Next(1, 29));
            salesData[i].departmentName = ProdDepartments.departmentNames[random.Next(0, ProdDepartments.departmentNames.Length)];
            int indexOfDept = Array.IndexOf(ProdDepartments.departmentNames, salesData[i].departmentName);
            string deptAbb = ProdDepartments.departmentAbbreviations[indexOfDept];
            string firstDigit = (indexOfDept + 1).ToString();
            string nextTwoDigits = random.Next(1, 100).ToString("D2");
            string sizeCode = new string[] { "XS", "S", "M", "L", "XL" }[random.Next(0, 5)];
            string colorCode = new string[] { "BK", "BL", "GR", "RD", "YL", "OR", "WT", "GY" }[random.Next(0, 8)];
            string manufacturingSite = ManufacturingSites.manufacturingSites[random.Next(0, ManufacturingSites.manufacturingSites.Length)];
            salesData[i].productID = $"{deptAbb}-{firstDigit}{nextTwoDigits}-{sizeCode}-{colorCode}-{manufacturingSite}";
            salesData[i].quantitySold = random.Next(1, 101);
            salesData[i].unitPrice = random.Next(25, 300) + random.NextDouble();
            salesData[i].baseCost = salesData[i].unitPrice * (1 - (random.Next(5, 21) / 100.0));
            salesData[i].volumeDiscount = (int)(salesData[i].quantitySold * 0.1);
        }
        return salesData;
    }

    ```

1. Enregistrez vos modifications.

### Mettre à jour la méthode QuarterlySalesReport en utilisant la conversation incluse

Vous devez mettre à jour la méthode `QuarterlySalesReport`. En fonction des objectifs du projet, vous devez implémenter les mises à jour suivantes :

- Lorsque vous affichez les résultats des ventes, listez les résultats dans un ordre logique. Par exemple, lorsque vous listez les ventes totales par trimestre, les trimestres doivent être listés dans l’ordre Q1 à Q4.
- Affichez les valeurs monétaires en utilisant les paramètres régionaux.
- Ajouter des calculs du bénéfice et du pourcentage de bénéfice trimestriels
- Ajoutez des calculs spécifiques aux services individuels : ventes, bénéfice et pourcentage de bénéfice trimestriels.
- Ajoutez des calculs pour des emplacements de fabrication spécifiques : ventes, bénéfice et pourcentage de bénéfice trimestriels.

À ce stade, votre méthode `QuarterlySalesReport` doit ressembler à l’extrait de code suivant :

```csharp

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
        Console.WriteLine("{0}: ${1}", quarter.Key, quarter.Value);
    }
}

```

Pour mettre à jour la méthode `QuarterlySalesReport`, procédez comme suit :

1. Pour vérifier la sortie du rapport des ventes trimestrielles à jour, exécutez l’application.

    Vous devriez voir une liste des résultats de ventes trimestrielles affichés dans la fenêtre de la console. Des valeurs aléatoires sont utilisées, de sorte que les données numériques varient à chaque exécution.

    La sortie du rapport des ventes trimestrielles doit ressembler à ce qui suit :

    ```output
    Quarterly Sales Report
    ----------------------
    Q3: $2060165.1045630067
    Q2: $2000706.5521363618
    Q4: $2168920.603583816
    Q1: $2174302.3663762277
    ```

    Remarquez que les trimestres ne sont pas listés dans l’ordre et que les valeurs monétaires ne sont pas correctement mises en forme.

    Votre première tâche consiste à résoudre ces problèmes.

1. Localisez la méthode `QuarterlySalesReport` dans le fichier Program.cs.

1. Sélectionnez la méthode entière.

1. Ouvrez l’interface de conversation inlined, puis entrez l’invite suivante :

    ```output
    Update the QuarterlySalesReport method to display quarterly results in order. Format currency using regional settings. 
    ```

1. Prenez un moment pour examiner les suggestions fournies par GitHub Copilot.

    Vous devriez voir une suggestion qui inclut le code nécessaire pour calculer le bénéfice et le pourcentage du bénéfice trimestriels. La suggestion doit inclure le code nécessaire pour calculer le bénéfice et le pourcentage de bénéfice pour chaque trimestre.

1. Pour accepter la suggestion fournie par GitHub Copilot, sélectionnez **Accepter**.

1. Enregistrez vos modifications.

1. Exécutez l’application et vérifiez que les résultats des ventes trimestrielles sont désormais affichés dans l’ordre et que les valeurs monétaires sont correctement mises en forme.

    Bien que les valeurs numériques soient différentes, la sortie du rapport des ventes trimestrielles doit maintenant être mise en forme comme la sortie suivante :

    ```output
    Quarterly Sales Report
    ----------------------
    Q1: $2,174,302.37
    Q2: $2,000,706.55
    Q3: $2,060,165.10
    Q4: $2,168,920.60

    ```

    L’étape suivante consiste à ajouter des calculs pour le bénéfice et le pourcentage de bénéfice trimestriels.

1. Localisez la méthode `QuarterlySalesReport` dans le fichier Program.cs.

1. Sélectionnez la méthode entière.

1. Ouvrez l’interface de conversation inlined, puis entrez l’invite suivante :

    ```output
    Update the QuarterlySalesReport method to include calculations for quarterly profit and profit percentage. Include the new calculations in the report output.
    ```

1. Prenez un moment pour examiner les suggestions fournies par GitHub Copilot.

    Vous devriez voir une suggestion qui inclut le code nécessaire pour calculer le bénéfice et le pourcentage du bénéfice trimestriels. La suggestion doit inclure le code nécessaire pour calculer le bénéfice et le pourcentage de bénéfice pour chaque trimestre.

1. Pour accepter la suggestion fournie par GitHub Copilot, sélectionnez **Accepter**.

1. Continuez à sélectionner **Accepter** pour les suggestions restantes.

1. Enregistrez vos modifications.

1. Exécutez l’application et vérifiez que les résultats des ventes trimestrielles incluent désormais les calculs du bénéfice et du pourcentage de bénéfice.

    Bien que les valeurs numériques soient différentes, la sortie du rapport des ventes trimestrielles doit maintenant être mise en forme comme la sortie suivante :

    ```output
    Quarterly Sales Report
    ----------------------
    Q1: Sales: $1,881,091.17, Profit: $231,351.24, Profit Percentage: 12.00%
    Q2: Sales: $1,949,240.91, Profit: $244,649.35, Profit Percentage: 11.00%
    Q3: Sales: $2,298,017.35, Profit: $273,622.53, Profit Percentage: 5.00%
    Q4: Sales: $2,279,185.96, Profit: $272,548.80, Profit Percentage: 16.00%    

    ```

    L’étape suivante consiste à ajouter des calculs pour les ventes, le bénéfice et le pourcentage de bénéfice trimestriels, par service.

1. Sélectionnez la méthode entière.

1. Pour ouvrir l’interface de conversation inlined, puis entrez l’invite suivante :

    ```output
    Update the QuarterlySalesReport method to include calculations for quarterly sales, profit, and profit percentage by department. Include the new calculations in the report output. 
    ```

1. Prenez un moment pour examiner les suggestions fournies par GitHub Copilot.

    Vous devriez voir une suggestion qui inclut le code nécessaire pour calculer le bénéfice et le pourcentage du bénéfice trimestriels. La suggestion doit inclure le code nécessaire pour calculer le bénéfice et le pourcentage de bénéfice pour chaque trimestre.

1. Pour accepter la suggestion fournie par GitHub Copilot, sélectionnez **Accepter**.

1. Continuez à sélectionner **Accepter** pour les suggestions restantes.

1. Enregistrez vos modifications.

1. Exécutez l’application et vérifiez que les résultats des ventes trimestrielles incluent désormais les calculs du bénéfice et du pourcentage de bénéfice.

    Bien que les valeurs numériques soient différentes, la sortie du rapport des ventes trimestrielles doit maintenant être mise en forme comme la sortie suivante :

    ```output
    Quarterly Sales Report
    ----------------------
    Q1: Sales: $2,043,493.57, Profit: $262,571.72, Profit Percentage: 14.00%
    By Department:
    Department: Accessories, Sales: $188,977.90, Profit: $25,229.53, Profit Percentage: 14.00%
    Department: Children's Clothing, Sales: $186,552.49, Profit: $25,511.74, Profit Percentage: 13.00%
    Department: Footwear, Sales: $293,706.49, Profit: $39,224.99, Profit Percentage: 19.00%
    Department: Men's Clothing, Sales: $301,385.47, Profit: $36,756.06, Profit Percentage: 19.00%
    Department: Outerwear, Sales: $238,099.65, Profit: $24,371.92, Profit Percentage: 15.00%
    Department: Sportswear, Sales: $251,349.38, Profit: $34,142.40, Profit Percentage: 8.00%
    Department: Undergarments, Sales: $297,690.60, Profit: $35,305.13, Profit Percentage: 9.00%
    Department: Women's Clothing, Sales: $285,731.58, Profit: $42,029.95, Profit Percentage: 19.00%
    
    Q2: Sales: $1,925,948.90, Profit: $232,929.95, Profit Percentage: 17.00%
    By Department:
    Department: Accessories, Sales: $251,572.42, Profit: $33,250.17, Profit Percentage: 11.00%
    Department: Children's Clothing, Sales: $311,862.99, Profit: $36,537.33, Profit Percentage: 8.00%
    Department: Footwear, Sales: $203,148.87, Profit: $23,041.46, Profit Percentage: 11.00%
    Department: Men's Clothing, Sales: $229,781.14, Profit: $26,226.68, Profit Percentage: 9.00%
    Department: Outerwear, Sales: $211,610.47, Profit: $23,684.65, Profit Percentage: 9.00%
    Department: Sportswear, Sales: $204,083.63, Profit: $20,750.56, Profit Percentage: 8.00%
    Department: Undergarments, Sales: $264,733.26, Profit: $35,155.66, Profit Percentage: 15.00%
    Department: Women's Clothing, Sales: $249,156.13, Profit: $34,283.45, Profit Percentage: 17.00%
    
    Q3: Sales: $2,113,223.50, Profit: $256,591.16, Profit Percentage: 7.00%
    By Department:
    Department: Accessories, Sales: $288,161.91, Profit: $32,279.54, Profit Percentage: 10.00%
    Department: Children's Clothing, Sales: $198,313.55, Profit: $24,146.72, Profit Percentage: 7.00%
    Department: Footwear, Sales: $205,840.60, Profit: $27,630.49, Profit Percentage: 5.00%
    Department: Men's Clothing, Sales: $229,279.26, Profit: $26,618.62, Profit Percentage: 13.00%
    Department: Outerwear, Sales: $353,696.46, Profit: $44,634.82, Profit Percentage: 14.00%
    Department: Sportswear, Sales: $229,490.12, Profit: $27,697.91, Profit Percentage: 5.00%
    Department: Undergarments, Sales: $316,942.44, Profit: $40,518.71, Profit Percentage: 5.00%
    Department: Women's Clothing, Sales: $291,499.15, Profit: $33,064.35, Profit Percentage: 10.00%
    
    Q4: Sales: $1,896,279.88, Profit: $248,226.28, Profit Percentage: 15.00%
    By Department:
    Department: Accessories, Sales: $336,698.68, Profit: $44,714.55, Profit Percentage: 11.00%
    Department: Children's Clothing, Sales: $193,345.18, Profit: $23,261.33, Profit Percentage: 13.00%
    Department: Footwear, Sales: $215,183.23, Profit: $29,616.00, Profit Percentage: 15.00%
    Department: Men's Clothing, Sales: $171,663.38, Profit: $24,299.37, Profit Percentage: 5.00%
    Department: Outerwear, Sales: $229,791.52, Profit: $28,211.17, Profit Percentage: 15.00%
    Department: Sportswear, Sales: $230,031.90, Profit: $32,732.40, Profit Percentage: 8.00%
    Department: Undergarments, Sales: $300,824.19, Profit: $34,649.79, Profit Percentage: 6.00%
    Department: Women's Clothing, Sales: $218,741.80, Profit: $30,741.67, Profit Percentage: 20.00%

    ```

### Résumé

Dans cette version de démonstration, vous avez utilisé la fonctionnalité de conversation incluse pour mettre à jour les méthodes `GenerateSalesData` et `QuarterlySalesReport`. Vous avez ajouté de nouveaux champs à la structure de données `SalesData`, puis mis à jour la méthode `GenerateSalesData` pour générer des données pour les nouveaux champs. Vous avez également mis à jour la méthode `QuarterlySalesReport` pour inclure des calculs pour le bénéfice et le pourcentage de bénéfice trimestriels. Vous avez également ajouté des calculs pour les ventes, le bénéfice et le pourcentage de bénéfice trimestriels, par service.
