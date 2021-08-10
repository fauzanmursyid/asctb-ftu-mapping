# Anatomical structure, Cell types and Biomarkers (ASCT+B) to Functional tissue unit (FTU) mapping

## Technical Description

The HuBMAP project aims to develop a map of the human body at the single-cell level. Currently, the project has developed an ASCT+B table that captures the anatomical structures, cell types, and biomarkers used to identify cell types inside the human body. To create a Google Map-like human atlas, a crosswalk table is needed to map the information in the ASCT+B table to highly detailed images of the human body. The images are in Scalable Vector Graphics (SVG) format for two reasons: it is scalable, and each element of the image can be referred to with an uberon or cell ontology ID. The crosswalk table will map between the components in the ASCT+B table and these IDs in the SVG images. As a starting point, we will focus on four anatomical structures: kidney nephron and renal corpuscle, lung alveoli, and large intestine colonic crypts. 

## Table Format

For each microanatomical structure, we create two tables: SVG description and ASCT+B-SVG Reference Object Ontology Crosswalk table.

The SVG description table maps the node names in the SVG to their respective reference name. Each AS and each CT have one reference name. This description table is created so the crosswalk table has one row per unique AS and CT. The table contains two columns:
1. svg_id: describes the node IDs of each AS/CT object on the SVG image files
2. reference_name: is the unique label given for each AS/CT

The second table is the crosswalk table. This table maps the description table to the ASCT+B table and consists of six columns:
1. reference_name: the reference_name from the description table
2. label: describes the name in the UBERON (for AS) and CL (for CT) ontologies
3. OntologyID: describes the IDs of the UBERON (for AS) and CL (for CT) ontologies
4. representation_of: describes the persistent uniform resource locator (PURL) of the UBERON (for AS) and CL (for CT) ontologies
5. exist_asctb: the value is 1 if the object has been registered in the ASCT+B table, and 0 if the object has not been registered
6. type: AS if the object is an anatomical structure, and CT if the object is a cell type

## Renal Corpuscle

Crosswalk table: https://raw.githubusercontent.com/fauzanmursyid/asctb-ftu-mapping/main/kidney-renal_corpuscle-ACST%2BB-SVG-Crosswalk.csv

Important notes:
Some anatomical structures were not represented by any object in the original SVG image. For example, Bowman's space is a space between the visceral and parietal layers, so there was no ID from the SVG image to represent this AS. As the solution, we created a transparent path in the SVG file to represent this space. 

Original SVG image from KPMP [^1]: https://raw.githubusercontent.com/fauzanmursyid/asctb-ftu-mapping/main/Schematics_Renal%20Corpuscle%20-%20human.svg
Edited version: https://raw.githubusercontent.com/fauzanmursyid/asctb-ftu-mapping/main/edited_Schematics_Renal%20Corpuscle%20-%20human.svg

Changes from the original SVG files:
1. path4883 represents Bowman's space. Reason for addition: not represented by any object in the original SVG image.
2. path17383 represents extraglomerular mesangium. Reason for addition: some parts of it are not represented by any object in the original SVG image.
3. Rename path and group id to resemble the AS/CT name

## Alveoli

Crosswalk table: https://raw.githubusercontent.com/fauzanmursyid/asctb-ftu-mapping/main/lung-alveoli-ACST%2BB-SVG-Crosswalk.csv

Important notes:
1. The mesenchymal parts in the ASCT+B table (secondary crest myofibroblasts, lung matrix fibroblast 2, lung matrix fibroblast 1/(Lipofibroblast?)) are not depicted on the SVG image, so we could not map them in this table.
2. There are two different capillarry endothelial cells in ASCT+B table: CAP1 and CAP2. Apart from their gene biomarkers expression, we are not aware of any morphological differences between them. So we could not map these CTs in the crosswalk table, and map their AS (pulmonary capilllary) instead.

Original SVG image from EBI [^2] : https://raw.githubusercontent.com/fauzanmursyid/asctb-ftu-mapping/main/alveoli.svg 
Edited version: https://raw.githubusercontent.com/fauzanmursyid/asctb-ftu-mapping/main/alveoli_colored.svg

Changes from the original SVG files:
1. Remove the original color and replace it with five colors to distinguish between CTs.
2. Add text label for each CT and AS.

## Colonic Crypts

Crosswalk table: https://raw.githubusercontent.com/fauzanmursyid/asctb-ftu-mapping/main/colon-crypts-ACST%2BB-SVG-Crosswalk.csv

Important notes:
The tuft cells and eosinophils are not depicted on the SVG image.

Original SVG image created with BioRender [^3] : https://github.com/fauzanmursyid/asctb-ftu-mapping/raw/main/crypt.PNG 
Edited version: https://raw.githubusercontent.com/fauzanmursyid/asctb-ftu-mapping/main/crypts_grouped.svg

Changes from the original SVG files:
1. The original image is a raster, so we vectorize it using Adobe Illustrator with 6 colors and automatically group the paths based on their filled color.
2. Relabel each CT.

## Nephron Tubules

Crosswalk table: https://raw.githubusercontent.com/fauzanmursyid/asctb-ftu-mapping/main/kidney-nephron_tubules-ACST%2BB-SVG-Crosswalk.csv

Important notes:
The image only captures the AS level; the image scale does not capture CT.

Original SVG image from KPMP [^1] : https://raw.githubusercontent.com/fauzanmursyid/asctb-ftu-mapping/main/KPMP_Schematics_Nephron%20tubules%20-%20human.svg
Edited image: https://raw.githubusercontent.com/fauzanmursyid/asctb-ftu-mapping/main/edited_Schematics_Nephron%20tubules%20-%20human.svg

Changes from the original SVG files:
1. removing spaces on these labels: metadata, nephron title, distal convoluted tubule, proximal straight tubule (S3)

## Reference

[^1]: Kidney Precision Medicine Project. Welcome to the Kidney Precision Medicine Project. (n.d.). https://www.kpmp.org/. 

[^2]: –&nbsp;https://www.ebi.ac.uk/about/people/irene-papatheodorou, E. B. I. G. E. T. (n.d.). Single&nbsp;Cell Expression&nbsp;Atlas. Experiment. https://www.ebi.ac.uk/gxa/sc/experiments/E-GEOD-130148/results/anatomogram. 

[^3]: BioRender. (n.d.). https://biorender.com/. 
