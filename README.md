# Anatomical structure, Cell types and Biomarkers (ASCT+B) to Functional tissue unit (FTU) mapping

## Technical Description

The HuBMAP project aims to develop a reference atlas the human body at the single-cell level. ASCT+B tables capture the anatomical structures (AS), their cell types (CT), and biomarkers used to identify cell types for different organs. The information in the ASCT+B table can be linked to detailed 2D (textbook) images of the human body. The images are provided in Scalable Vector Graphics (SVG) format and each component of the image is named. A crosswalk table maps image components to ASCT+B table IDs. Note that an SVG figure can have multiple components of the same AS or CT type. As a starting point, we focus on functional tissue units (FTU) such as kidney nephron and renal corpuscle, lung alveoli, and large intestine colonic crypts. 

## Table Format

For each FTU, we create two files: SVG file that describes the 2D outlines of major anatomical structures and cell types and a crosswalk table in the CSV format that describes the mapping of 2D SVG Reference Object components to unique AS/CT in the ASCT+B  table.
Each CSV file has nine columns: 

1.	svg_id: describes the path/group IDs of each AS/CT object on the SVG image files
2.	label: describes the name of each AS/CT in the UBERON and CL ontologies
3.	OntologyID: describes the IDs of the UBERON and CL ontologies
4.	representation_of: describes the persistent uniform resource locator (PURL) of the UBERON and CL ontologies
5.	exist_asctb: the value is 1 if the object has been registered in the ASCT+B table, and 0 if the object has not been registered
6.	type: AS if the object is an anatomical structure, and CT if the object is a cell type
7.	REF: describes the reference information for each AS/CT
8.	REF/DOI: describes the DOI (if any) of the reference information for each AS/CT
9.	REF/NOTES: additional notes (if any) for the reference information of each AS/CT

## Kidney's Glomeruli

Crosswalk table: https://raw.githubusercontent.com/fauzanmursyid/asctb-ftu-mapping/main/v1.0/2d-models/kidney-glomeruli.mapping.csv

Original SVG image from KPMP [^1]: [https://raw.githubusercontent.com/fauzanmursyid/asctb-ftu-mapping/main/original_image/Schematics_Renal%20Corpuscle%20-%20human.svg](https://raw.githubusercontent.com/fauzanmursyid/asctb-ftu-mapping/main/original_image/Schematics_Renal Corpuscle - human.svg)

Edited SVG image: https://raw.githubusercontent.com/fauzanmursyid/asctb-ftu-mapping/main/v1.0/2d-models/kidney-glomeruli.svg

Changes from the original SVG file:

1. Add new path with svg_id=”Bowman's_space” to represent     Bowman's space AS. Reason for addition: not represented by any object in     the original SVG image.
2. Add new path with svg_id=”extraglomerular_mesangium_1” to     represent extraglomerular mesangium. Reason for addition: not represented     by any object in the original SVG image.
3. Renamed these path and group IDs to resemble the AS/CT name: path571, path573, path17383, path45, path43, path4883, path191, path195, path199, path203, path207, path211, path215, path219, path223, path227, path231, path235, path239, path635, path631, path627, path623, path619, path615, path611, path607, path603, path599, path595, path591, path587, path583, path579, path571, path573, path49, path51, path53, path55, path57, path61, path63, path65, path67, path69, path71, path73, path75, path103.

------

## Lung's Alveoli

Crosswalk table: https://raw.githubusercontent.com/fauzanmursyid/asctb-ftu-mapping/main/v1.0/2d-models/lung-alveoli.mapping.csv

Original SVG image from EBI [^2]: https://raw.githubusercontent.com/fauzanmursyid/asctb-ftu-mapping/main/original_image/alveoli.svg

Edited SVG image: https://raw.githubusercontent.com/fauzanmursyid/asctb-ftu-mapping/main/v1.0/2d-models/lung-alveoli.svg

Important notes:

1. The mesenchymal parts in the ASCT+B table (secondary     crest myofibroblasts, lung matrix fibroblast 2, lung matrix fibroblast     1/(Lipofibroblast?)) are not depicted on the SVG image, so we could not     map them in this table.
2. There are two different capillary endothelial cells in     ASCT+B table: CAP1 and CAP2. Apart from their gene biomarkers expression,     we are not aware of any morphological differences between them. So we     could not map these CTs in the crosswalk table, and map their AS     (pulmonary capillary) instead.

Changes from the original SVG file:

1. Replace the original colors with five colors to     distinguish between CTs.
2. Added text label for each CT and AS.
3. Renamed these path and group ids to resemble the AS/CT name: LAYER_EFO, g14, g18, g10, g6, path71, CL_0002062, CL_0002063, g79, g83, path74

## Large Intestine's Crypts

Crosswalk table: https://raw.githubusercontent.com/fauzanmursyid/asctb-ftu-mapping/main/v1.0/2d-models/intestine_large-crypts.mapping.csv

Original SVG image created with BioRender [^3] : https://github.com/fauzanmursyid/asctb-ftu-mapping/blob/main/original_image/crypt.PNG

Edited SVG image: https://raw.githubusercontent.com/fauzanmursyid/asctb-ftu-mapping/main/v1.0/2d-models/intestine_large-crypts.svg

Important notes: The tuft cells and eosinophils are not depicted on the SVG image.

Changes from the original SVG file:

1. The original image is a raster, so we vectorized it     using Adobe Illustrator with 6 colors and automatically group the paths     based on their filled color.
2. Relabeled each CT.

## Kidney's Nephron Tubules

Crosswalk table: https://raw.githubusercontent.com/fauzanmursyid/asctb-ftu-mapping/main/v1.0/2d-models/kidney-nephron_tubules.mapping.csv

Original SVG image from KPMP [^1] : [https://raw.githubusercontent.com/fauzanmursyid/asctb-ftu-mapping/main/original_image/KPMP_Schematics_Nephron%20tubules%20-%20human.svg](https://raw.githubusercontent.com/fauzanmursyid/asctb-ftu-mapping/main/original_image/KPMP_Schematics_Nephron tubules - human.svg)

Edited SVG image: https://raw.githubusercontent.com/fauzanmursyid/asctb-ftu-mapping/main/v1.0/2d-models/kidney-nephron_tubules.svg

Changes from the original SVG files:

1. Removed spaces on these labels: metadata, nephron     title, distal convoluted tubule, proximal straight tubule (S3).

## Reference

[^1]: Kidney Precision Medicine Project. Welcome to the Kidney Precision Medicine Project. (n.d.). https://www.kpmp.org/. 

[^2]: –&nbsp;https://www.ebi.ac.uk/about/people/irene-papatheodorou, E. B. I. G. E. T. (n.d.). Single&nbsp;Cell Expression&nbsp;Atlas. Experiment. https://www.ebi.ac.uk/gxa/sc/experiments/E-GEOD-130148/results/anatomogram. 

[^3]: BioRender. (n.d.). https://biorender.com/. 
