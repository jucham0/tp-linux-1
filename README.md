# Admin Post *Client* [**Linux**]

Savoir **manager** du client et du serveur focalisation du management **client**

## 🤵John DREYFUS

- Dev FullStack
- Ancien d'Ynov
- *Comunication :*  Teams / Discord/ Mail

## Sommaire | Intro

### 🐾 5 seances :
- Intro **Linux** et **commandes** de base
- gestion **user** et **droits**
- gestion **processus** et des **filtres**
- gestion des packets et **SSH**
- **TP** noté

## TP 1.1
### 🗃️ Setup
```bash
$ whoami -> julien
$ hostname -> debian
$ pwd -> /home/julien
```

### 2) 📂 Test
```bash
$ cd / -> julien@debian:/$
$ ls -> Listage des different fichiers et dossiers dans le repertoire
$ cd -> Vide
$ cd ~ -> Apparition de la ~ julien@debian:~$
```

### 3) 🔧 Mainipulation
```bash
$ mkdir mon_premier_repertoire
$ cd mon_premier_repertoire
$ touch mon_premier_fichier.txt
$ ls 
	 mon_premier_fichier.txt 
```



## TP1.2
### Manip Files & Dir

#### 🌳 Tree
```bash
$ sudo apt update -y && sudo apt install -y tree
$ tree 
.
└──mon_premierrepertoire
	└──mon_premier_fichier.txt
2 directories, 1 file
```
#### ➡️ Suite 
```bash
$ ls 
	 mon_premier_repertoire

$ mkdir mon_second_repertoire
$ cd mon_second_repertoire/
$ touch file1.txt file.2txt file3.txt
$ ls 
	 file1.txt file.2txt file3.txt

$ mv file1.txt file1_rename.txt
$ ls 
	 file1_rename.txt file.2txt file3.txt
$ cp file1_rename.txt copie_fichier.txt
$ ls 
	 copie_fichier.txt file1_rename.txt file.2txt file3.txt

$ rm copie_fichier.txt
$ ls 
	 file1_rename.txt file.2txt file3.txt

$ mkdir sous_repertoire
$ ls 
	 file1_rename.txt file.2txt file3.txt sous_repertoire

$ mv file2.txt file3.txt sous_repertoire
$ ls 
	 file1_rename.txt sous_repertoire
```
 ***mv*** -> Permet de **déplacer** / **renommer** des fichiers (**manipulations de fichiers et dossiers**)

#### 👀Visualisation
```bash
$ cd ../
$ tree
.
└──mon_premier_repertoire
	└──mon_premier_fichier.txt
└──mon_second_repertoire
	└──file1.rename.txt
	└──sous_repertoire
		└──file2.txt
		└──file3.txt
		
4 directories, 4 files
``` 
#### ➕📂 mkdir
```bash
$ mkdir dossier1/dossier2
	mkdir: impossible de créer le répertoire "dossier1/dossier2": Aucun fichier ou dossier de ce type

$ mkdir -p dossier1/dossier2
$ tree
.
└──dossier1
	└──dossier2
└──mon_premier_repertoire
	└──mon_premier_fichier.txt
└──mon_second_repertoire
	└──file1.rename.txt
	└──sous_repertoire
		└──file2.txt
		└──file3.txt
```

#### 📁 Répertoire test

```bash
$ mkdir test //on crée le répertoire test
$ rmdir test //on le supprime

```
#### 📂❌ rmdir

```bash
$ rmdir mon_premier_repertoire
	rmdir: impossible de supprimer 'mon_premier_repertoire': Le dossier nest pas vide

$ rm -r mon_premier_repertoire
$ ls 
	 dossier1 mon_second_repertoire
```

#### 🧹 Nettoyage
```bash
$ rm -r *
$ ls 
	 Rien
```


## TP1.3
### Exploration

#### 🧾 Manipulation
```bash
$ mdir projets
$ cd projets/
$ mkdir projet{1..3}
$ tree
.
└──projets
	└──projet1
	└──projet2
	└──projet3
```
#### 🧾 File A,B,C

```bash
$ touch file{A..C}.txt
$ ls
	fileA.txt fileB.txt fileC.txt
```

#### ➡️ Déplacer Fichiers

```bash
$ cd projets/projet1
$ mv fileB.txt ../projet2
$ cd ../
$ tree
.
└──projets
	└──projet1
		└──fileA.txt
		└──fileC.txt
	└──projet2
		└──fileB.txt
	└──projet3
```

#### 📜📜 Copie Fichier

```bash
$ cd projets/projets2
$ cp fileB.txt ../projet3
$ cd ../
$ tree
.
└──projets
	└──projet1
		└──fileA.txt
		└──fileC.txt
	└──projet2
		└──fileB.txt
	└──projet3
		└──fileB.txt
4 directories, 4 files
```