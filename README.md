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
- Lien du corpus: [[https://huggingface.co/datasets/samsum](https://huggingface.co/datasets/multi_news?row=5)](https://huggingface.co/datasets/multi_news)


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
