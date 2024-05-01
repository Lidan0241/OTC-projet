# Repo de projet - Outil de Traitement de Corpus - M1S2 TAL

## Tâche
### Summurization (résumé de texte)
- On décompose un dialogue long en paragraphes ou phrases en préservant le sens original du texte. Cela nous permet de réduire le temps de lecture sans perdre les informations essentielles.
### Sous-tâche: 
- **news-articles-summarization**:
Il consiste à créer des résumés concis et informatifs de longs articles de presse. Cela implique l'analyse du texte pour comprendre les points clés, puis la génération d'un résumé qui conserve les informations essentielles. Il y a deux approches principales : l'extraction, où des phrases entières sont tirées de l'article, et l'abstraction, où de nouvelles phrases sont générées pour représenter le contenu. 

## Corpus étudié
- Nom de dataset: multi_news
- Producteurs du langage: experts de presse, journalistes
- Format: articles - résumés
- taille: 10k<n<100k
- langue: anglais, monolingue
- 3 parties: train: 45k rows; dev: 5.62k rows; test: 5.62k rows
- Lien du corpus: https://huggingface.co/datasets/multi_news?row=0


## Étape de Résumé
- Nettoyage de texte
- Tokénisation de phrase -> de mots
- Tableau de fréquence de mots, extraction d'informations
- Résumé
  
## À quel type de prédiction sert-t-il?
- NER (reconnaissance d'entités nommées);
- classification de tokens;
  
## À quel modèle a-t-il servi?
biu-nlp/f-coref, Ssarion/gpt2-multi-news, ccdv/lsg-bart-base-4096-multinews

## À savoir sur le corpus
-Document : texte d'articles de presse séparés par le jeton spécial `|||||`.
- un ensemble de données composé d'articles de presse et de résumés écrits par des humains de ces articles, provenant du site newser.com. Chaque résumé est rédigé professionnellement par des rédacteurs et inclut des liens vers les articles originaux cités.

## 01/05/2024

### Web-scraping depuis Le Monde
- pour pouvoir trouver des ressources qui correspondent à mon corpus de référence: résumé + texte long, j'ai trouvé les articles sur le site Le Monde et extrait leur titre ainsi que leur contenu en utilisant les librairies requests et SeautifulSoup depuis une dizaine de site web

### Transormation en dataframe
- J'ai d'abord transformé les données scrapées en format json, ensuite j'ai utilisé pandas pour le retransformé en dataframe pour mieux voir les données en labélisant chaque données de `title` et `content`
- J'ai ainsi fait des analyses sur le nombre de mot de content et de title de chaque article, après visualization de matplotlib, la proportion de title dans chaque article prend 3.9% de taille par rapport à celle de content, ce qui paraît assez raisonnable.
- la tâche de repérer le mot le plus fréquent dans un article me paraît également pertinent dans le cadre de ce projet. J'ai donc utilisé nltk pour d'abord filtrer les stopwords de chaque contenu, ensuite lemmatizer chaque mot, et compter le mot le plus fréquent d'un article et sa fréquence. J'ai remarqué que le mot le plus fréquent apparaît souvent dans le titre. J'ai donc ajouté ces informations au dataframe.
