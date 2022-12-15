# Guide pour l'édition d'un texte XMLTei 
## Dans le cadre du projet Vortex

Les étape de ce guide d'édition (en construction) considère que l'instalation du logiciel Oxygen XML est complétée. Se référer à l'onglet [Pour télécharger Oxygen XML](https://github.com/emileca/vortex/blob/main/T%C3%A9l%C3%A9charger%20Oxygen%20XML%20Editor.md)pour les détails.

# Intégrer le texte à un fichier TEI
1. Ouvrez Oxygen XML .
2. Créez un nouveau document.
3. Lorsque l'éditeur vous demandera de "Choisir un modèle de fichier", choisissez a. **TEI/ALL** si vous éditez un texte en prose ou b. **TEI/Drama** si vous éditez une pièce de théâtre ou un dialogue (style platonicien). Si vous faites l'édition d'**images** vous devrez travailler averc un schema TEI sur mesure qui à été créé spécialement pour ce type de fichier. Vous le trouverez dans l'onglet `vortex/Schemas_TEI/desc.images`. Ne vous y attardez pas pour le moment, il s'agit d'un défi pour l'intégration que nous sommes en train de relever.
4. Une fois le fichier ouvert, enregistrez le dans votre ordinateur et donnez lui un nom suivant la nomanclature : AUTEUR.oeuvre.chant/chapitre/livre(langue de votre édition).
Vérifiez que le dossier est bien sauvegardé dans un endroit dont vous avez l'accès sur votre ordinateur.

#Débuter le balisage
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
         <p>Some text here.</p>
      </body>
  </text>
</TEI> 
```
