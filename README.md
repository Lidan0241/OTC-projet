# Repo de projet - Outil de Traitement de Corpus - M1S2 TAL

## Tâche
### Summurization (résumé de texte)
- On décompose un dialogue long en paragraphes ou phrases en préservant le sens original du texte. Cela nous permet de réduire le temps de lecture sans perdre les informations essentielles.
### Sous-tâche: 
- summurization-conversation (résumé/synthèse de dialogue): le processus qui consiste à résumer un dialogue afin d'avoir immédiatement une bonne compréhension de la conversation. Cela peut être employé dans la consultation médicale, l'entretien d'embauche, rapport de police etc.

## Corpus étudié
- Nom de dataset: SAMSum
- Producteurs du langage: linguistes
- Annotateurs de corpus: experts en linguistique
- Format: Dialogues
- taille: 10k<n<100k(16k conversations)
- langue: anglais, monolingue
- 3 parties: train: 14732; val: 818; test: 819
- Lien du corpus: https://huggingface.co/datasets/samsum

## Exemple
- ID: `13728867`
- DIALOGUE: `Olivia: Who are you voting for in this election? Oliver: Liberals as always. Olivia: Me too!! Oliver: Great`
- SUMMARY: `Olivia and Olivier are voting for liberals in this election.`

## Étape de Résumé
- Nettoyage de texte
- Tokénisation de phrase -> de mots
- Tableau de fréquence ede mots
- Résumé
  
## À quel type de prédiction sert-t-il?
- NER (reconnaissance d'entités nommées);
- classification de tokens;
  
## À quel modèle a-t-il servi?
bart-large-cnn-samsum(https://huggingface.co/philschmid/bart-large-cnn-samsum), pegasus-samsum, distilbart-cnn-12-6-samsum, bart_summarisation, etc.

## À savoir sur le corpus
- Il contient des conversations fictives avec leurs résumés associés. Les linguistes ont été invités à créer des conversations similaires à celles qu'ils écrivent quotidiennement, reflétant la proportion de sujets de leurs conversations de messagerie réelles. Les conversations peuvent être informelles, semi-formelles ou formelles, elles peuvent contenir des mots d'argot, des émoticônes et des fautes de frappe. Les conversations ont ensuite été annotées par des résumés. On a supposé que les résumés devaient être un résumé concis de ce dont les personnes avaient parlé dans la conversation à la troisième personne.
- L'ensemble de données créé est composé de 16369 conversations réparties uniformément en 4 groupes en fonction du nombre d'énoncés dans les conversations : 3-6, 7-12, 13-18 et 19-30.
