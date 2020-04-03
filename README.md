# Projet de détection de violence dans des tweets

SafeTweet est une application mobile pour Android qui permet à un utilisateur de Twitter de naviguer en toute sécurité sur ce-dit réseau social. L’application est un Twitter-like, c’est-à-dire, une application semblable à Twitter. Elle permet à son utilisateur de consulter sa timeline - Fil d’actualités - et d’informer (voire filtrer) le contenu qui peut s’avérer dangereux. Le domaine d’application des fake news étant très vaste, l’application a alors pour but de rassurer ou/et de prévenir les personnes victimes de harcèlement.

Pour faire cela nous avons fait :
 - Une application android : https://github.com/nouveliere-benjamin/Fake-News-2019_2020
 - Un notebook qui regroupe la création et l'entrainement du modèle LSTM ainsi que la Dataset utilise : https://github.com/nathan46/detection_tweet_violent_LSTM
 - Une Api python qui permet de faire le lien entre les deux : https://github.com/nathan46/api_flask_LSTM

# Notebook et Dataset
Pour créer le modèle final du projet, j'ai utilisé la dataset **data.csv** et j'ai mis au point le notebook **LSTM.ipynb**.
Pour gagner du temps lors de l'entrainement du modèle j'ai créer un fichier **cleanData.csv** qui est une copie de **data.csv** avec les données déjà nettoyées.

## Pour commencer

### Cloner le dépôt
```bash
$ git clone https://github.com/nathan46/detection_tweet_violent_LSTM.git
$ cd detection_tweet_violent_LSTM
```
### Installer les dépendances
```bash
$ sudo pip3 install -r requirements.txt
```

### Installer Jupyter Notebook

```bash
$ sudo pip3 install notebook
```

### Lancer Jupyter Notebook
Il suffit d'écrire cette commande dans le dossier **detection_tweet_violent_LSTM**
```bash
$ jupyter notebook
```
Un navigateur s'ouvre et il ne reste plus qu'à cliquer sur le fichier **LSTM.ipynb**

### Exécuter le code
Vous pouvez exécuter chaque cellule les unes à la suite des autres avec la commande :

<kbd>shift</kbd> + <kbd>enter</kbd>

Si vous voulez stopper une cellule, il suffit de cliquer en dehors de celle-ci et de faire :

<kbd>i</kbd> , <kbd>i</kbd>

## Quelques fonctions

### Faire une prédiction
Pour faire une prédiction il y la fonction :
```python
def predict(net, test_tweet, sequence_length=15):
``` 
- net -> le modèle entrainé
- test_tweet -> un tweet lambda
- sequence_length -> la longueur maximal du tweet (en accord avec celui utilisé pour l'entrainement)

### Enregistrer un modèle 

Pour enregistrer un modèle il faut appeler la fonction : 
```python
def saveModelAndVocab(net, name, vocab_to_int):
``` 
- net -> le modèle entrainé
- name -> un nom (le nom que vous allez utiliser dans l'Api)
- vocab_to_int -> le dictionnaire qui permet de convertir les mots en nombres 
