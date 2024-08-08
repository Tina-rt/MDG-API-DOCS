# MDG API DOCS

## Base url: 
`https://daily-mg-back.onrender.com`

## Endpoints

### Hot News

-   **GET** `/`
-   Tags: `News`
-   Responses:
    -   200: A dictionary containing all headlines (Madagascar and international).:
    ```js
    [
        {
            "created_at": "2024-08-04T16:32:26.656872+00:00",
            "publisher": {
                "id": 3,
                "name": "Le monde" 
            },
            "link": "https://www.lemonde.fr/international/article/2024/08/02/moscou-a-relache-ses-principaux-opposants-critiques-de-la-guerre_6264920_3210.html",
            "img": "https://img.lemde.fr/2024/08/02/23/0/3953/2635/315/210/75/0/ba0b58b_1722584028037-694222.jpg",
            "title": " La Russie a relâché ses principaux opposants critiques de la guerre  ",
            "detail": null,
            "published_at": null,
            "id": 194,
            "category": 2,
            "isTop": true, // Article pertinent
        },
        {
            "created_at": "2024-08-04T16:32:26.656872+00:00",
            "publisher": {
                "id": 1,
                "name": "L'express de Madagascar"
            },
            "link": "https://www.lexpress.mg/2024/08/festival-sobahya-la-culture-sakalava.html",
            "img": "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi7Ch41GvuVqaKvpKRiVXw9Z4Tzfj5ScGjx7BoHrWEaCnzP_Is4doxJFlAGtgFlpPJHQHz5J77ydxWlOPMriamt1UJmus37puM33RhgpSJ2BQu7puJXPKGRpTlUnVPqwgQeumzIAb_z-QAuRCy3os2M2snv4m-tXr7jxv-2FGT2d8n-wIKsJVbaYMsO2g3M/w72-h72-p-k-no-nu/1722615983132.jpg",
            "title": "FESTIVAL SOBAHYA  - La culture Sakalava Marambitsy sous divers angles",
            "detail": "Les organisateurs du festival Sobahya hier lors de la rencontre avec la presse au Telma Analakel…",
            "published_at": "2024-08-03",
            "id": 193,
            "category": 1
        }
    ]
    ```

### Detail Journal

-   **GET** `/detail`
-   Tags: `News`
-   Parameters:
    -   link: The link to the journal article. (required)
    -   journal_id: The ID of the journal. (required)
-   Responses:

    -   200: A dictionary containing the journal information.
    -   | Field     | Detail                      |
        | --------- | --------------------------- |
        | `content` | List of paragraph           |
        | `img`     | Link to the image cover     |
        | `date`    | Date of the article release |

        ```json
        {
            "content": [
                "La 18e édition du festival Sobahya, annoncée hier lors d’une conférence de presse à Analakely, se tiendra du 9 au 11 août à Katsepy pour mettre en lumière la culture Marambitsy.",
                "COMME le festival Sômarôho pour Nosy Be, le festival des Baleines pour Sainte-Marie, le festival Dola Beach pour Vatomandry, ou encore le festival Waka Waka pour Sambava, le Festival Sobahya de la région Boeny se prépare à enchanter les touristes pour sa 18e édition, qui se tiendra du 9 au 11 août à Katsepy. ",
                "      Ce festival vise à promouvoir le domaine touristique de Katsepy ainsi que la richesse culturelle du peuple Sakalava de Marambitsy à travers diverses activités. “Katsepy est la porte d’entrée de la région Marambitsy. Toute la culture de Marambitsy se reflète dans l’art culinaire, notamment grâce à l’ingrédient phare comme le coco, ainsi que dans les danses comme le Jijy, les stands d’exposition, les jeux traditionnels comme le moraingy, et les spectacles, y compris des défilés de mode présentant les tenues traditionnelles Sakalava”, explique Mokhtar Salim Andriatomanga, le gouverneur de la région Boeny, lors de la conférence de presse tenue au Rooftop Analakely en collaboration avec Telma Madagascar.",
                "L’objectif principal de ce festival est de mettre en avant la culture de Marambitsy et de la faire découvrir aux touristes, qu’ils soient locaux ou étrangers, en cette période de vacances où Mahajanga est une destination privilégiée à Madagascar.",
                " “Nous pouvons attirer des touristes grâce à ce festival. En collaboration avec les grands et moyens hôtels de Mahajanga, ce festival offre une occasion unique de découvrir la richesse culturelle et touristique de Marambitsy. Des navettes gratuites seront mises à disposition pour les déplacements entre Mahajanga et Katsepy pendant l’événement», souligne Eric Razafimaitra, représentant de l’Office régional du tourisme de Boeny.",
                "Le mot “Sobahya” provient du tissu emblématique des Sakalava et reflète l’histoire de l’Ampanjaka. Pour cette édition, des artistes de Mayotte comme Komo de Mayotte et Choc Choc de Mayotte, ainsi que des artistes locaux tels que Jean-Aimé et Matolahy, ont été invités à se produire. “Il y aura également un concours original pour élire le participant le plus moche”, ajoute Tantely Fanja Rafaraharinivo, directeur régional de la Communication et de la Culture de Boeny. Il est important de noter qu’à Katsepy, la consommation de certains aliments, tels que les pistaches, le porc et l’alcool, est interdite.",
                "Nicole Rafalimananjara"
            ],
            "img": "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi7Ch41GvuVqaKvpKRiVXw9Z4Tzfj5ScGjx7BoHrWEaCnzP_Is4doxJFlAGtgFlpPJHQHz5J77ydxWlOPMriamt1UJmus37puM33RhgpSJ2BQu7puJXPKGRpTlUnVPqwgQeumzIAb_z-QAuRCy3os2M2snv4m-tXr7jxv-2FGT2d8n-wIKsJVbaYMsO2g3M/s16000/1722615983132.jpg",
            "date": "2024-08-03T05:45:00+03:00"
        }
        ```

### International News

-   **GET** `/international`
-   Tags: `News`
-   Parameters:
    -   limit: The number of headlines to retrieve. (optional)
-   Responses:
    -   200: A dictionary containing the headlines.

### Olympics

-   **GET** `/olympics`
-   Tags: `Olympics`
-   Responses:
    -   200: A dictionary containing list of top 66 country in the Paris JO 2024
    ```json
      [
        {
          "disciplines": [] // List of disciplines, medals and categories
          "organisation": "CHN",
          "description": "China",
          "longDescription": "People's Republic of China",
          "nameOrder": 430,
          "longNameOrder": 1600,
          "protocolOrder": 41,
          "rank": 1,
          "rankEqual": false,
          "sortRank": 1,
          "rankTotal": 2,
          "rankTotalEqual": false,
          "sortTotalRank": 2,
          "medalsNumber": [
            {
                "type": "Total",
                "gold": 22,
                "silver": 19,
                "bronze": 14,
                "total": 55
            },
            {
                "type": "Women",
                "gold": 8,
                "silver": 10,
                "bronze": 8,
                "total": 26
            },
            {
                "type": "Mixed",
                "gold": 3,
                "silver": 2,
                "bronze": 1,
                "total": 6
            },
            {
                "type": "Men",
                "gold": 11,
                "silver": 7,
                "bronze": 5,
                "total": 23
            }
        ]
        }
      ]
    ```

### Update Local and international news Database

-   **GET** `/updateDb`
-   Tags: `UpdateDb`
-   Responses:
    -   200: `{'msg': 'Data inserted'}`

### Update news Category database

-   **GET** `/updateDb/{news_category}`
-   Tags: `InsertDB`
-   Responses:
    -   200: `{'msg': 'Local Headlines inserted'}` / `{'msg': 'International Headlines inserted'}` / `{'msg': 'Invalid category'}`

## Some infos

-   _Category_ :
