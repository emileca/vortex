# Guide pour l'édition d'un texte XMLTei 
## Dans le cadre du projet Vortex

Les étape de ce guide d'édition (en construction) considère que l'instalation du logiciel Oxygen XML est complétée. Se référer à l'onglet [Pour télécharger Oxygen XML](https://github.com/emileca/vortex/blob/main/T%C3%A9l%C3%A9charger%20Oxygen%20XML%20Editor.md)pour les détails.

# Intégrer le texte à un fichier TEI
1. Ouvrez Oxygen XML .
2. Créez un nouveau document.
3. Lorsque l'éditeur vous demandera de "Choisir un modèle de fichier", choisissez a. **TEI/ALL** si vous éditez un texte en prose ou b. **TEI/Drama** si vous éditez une pièce de théâtre ou un dialogue (style platonicien). Si vous faites l'édition d'**images** vous devrez travailler averc un schema TEI sur mesure qui à été créé spécialement pour ce type de fichier. Vous le trouverez dans l'onglet `vortex/Schemas_TEI/desc.images`. Ne vous y attardez pas pour le moment, il s'agit d'un défi pour l'intégration que nous sommes en train de relever.
4. Une fois le fichier ouvert, enregistrez le dans votre ordinateur et donnez lui un nom suivant la nomanclature : AUTEUR.oeuvre.chant/chapitre/livre(langue de votre édition). *NOTEZ QUE VOUS DEVEZ FAIRE UN DOCUMENT POUR CHAQUE CHAPITRE/LIVRE/CHANT. PAR EXEMPLE, LE FICHIER `HOMERE.iliade.1` NE DEVRAIT CONTENIR QUE LE PREMIER CHANT DE L'ILIADE.* **Utiliser lez chiffres arabes pour numéroter les divisions**
Vérifiez que le dossier est bien sauvegardé dans un endroit dont vous avez l'accès sur votre ordinateur.

# Ajouter le texter au fichier XML.TEI
1. L'ajout des balise est le coeur de notre travail. Des balises non-conformes aurait pour conséquance la perte des valeurs de votre textes puisque la base de donnée ne serait pas cappable d'en faire la lecture.
2. Sur votre document, vous devriez avoir d'afficher les lignes suivantes : 
``` 
<?xml version="1.0" encoding="UTF-8"?>
<?xml-model href="http://www.tei-c.org/release/xml/tei/custom/schema/relaxng/tei_all.rng" type="application/xml" schematypens="http://relaxng.org/ns/structure/1.0"?>
<?xml-model href="http://www.tei-c.org/release/xml/tei/custom/schema/relaxng/tei_all.rng" type="application/xml"
	schematypens="http://purl.oclc.org/dsdl/schematron"?>
<TEI xmlns="http://www.tei-c.org/ns/1.0">
  <teiHeader>
      <fileDesc>
         <titleStmt>
            <title>Title</title>
         </titleStmt>
         <publicationStmt>
            <p>Publication Information</p>
         </publicationStmt>
         <sourceDesc>
            <p>Information about the source</p>
         </sourceDesc>
      </fileDesc>
  </teiHeader>
  <text>
      <body>
         <p>** Some text here. **</p>
      </body>
  </text>
</TEI> 
```
3. À l'endroit ou il est écrit ***Some text here.*** venez coller le texte de votre chapitre/chant/livre.
4. Vous êtes maintenant près à débuter le balisage TEI.

# Balisage du texte (à venir)
Une rencontre sera tenue avec les édit.rice.eur.s dans le but vous former à l'utilisation de la TEI. Si vous désirez commencer à explorer l'univers de la TEI, vous pouvez vous référer au site des [*guidelines* de la TEI](https://tei-c.org/release/doc/tei-p5-doc/en/html/index.html). *À ce moment, SVP, ne rien commuter dans la branche `main` du `git`.

# `Git-push` vers votre propre branche
1. Lorsque vous avez terminer l'édition d'un texte, c'est le moment de l'ajouter au `git` qui constitura la base de donnée hébergée sur [BaseX](https://basex.org/). Dans le ficher de votre auteur, vous trouverez deux document : un pour le texte en langue ancienne et un pour le texte en langue moderne. Ne cliquer pas sur les documents
2. Demeurez dans le dossier ou s'affiche les deux documents et cliquer sur ***New File***. Une nouveau document sera créé.
3. Dans l'espace de nom (ou les éléments `vortex/Aristote` apparaissent), écrivez le nom de votre auteur en choisissant a. FR EN pour les textes en francais et en anglais ou b. GRC LAT pour les textes en langues anciennes.
4. Appuyez sur la barre oblique (/) et un nouvel espace de nom apparaitera.
5. Entrez là le nom de votre fichier en suivant la nomenclature de départ (AUTEUR.oeuvre.chant/chapitre/livre(langue de votre édition)).
6. Glissez fichier XML que vous avez créé avec Oxygen dans l'espace de code (*vous pouvez aussi copier/coller l'entièreté du texte*).
7. C'est maintenant le moment de *merger* sur votre branche personnelle (!!!jamais dans la `main`!!!). Si il s'agit de votre premier dépôt, dans le bas de la page, cliquez sur *"Create a new branch for this commit and start a pull request"* en nommez là : *votre nom*-patch-1
8. Lorsque vous reviendrez travaillez sur le `git` à l'espace `emileca/vortex`, vous verrez, sous le menu "code" et "issues" un menu déroulant vous permettant de choisir la branche sur laquelle vous travaillez. Votre branche devrait si trouver. Il s'agit de votre espace de travail auquel tout le monde peut profiter de vos édition. Assurez vous de toujours travailler sur votre branche. Advenant une erreur (création d'une nouvelle branche ou *push* dans la `main`), avisez Émile le plus rapidement pour éviter que d'autres édit.rice.eur.s poursuivent le travail dans cet espace.

Pour plus d'information sur le fonctionement de `git`, voir le [petit guide](https://rogerdudler.github.io/git-guide/index.fr.html) qui demeurt somme toute assez complet et facile d'approche.

Bon travail!
