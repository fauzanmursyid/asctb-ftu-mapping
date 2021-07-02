# asctb-ftu-mapping

## Technical Description

The HuBMAP project aims to develop a map of the human body at the single-cell level. Currently, the project has developed an ASCT+B table that captures the anatomical structures, cell types, and biomarkers used to identify cell types inside the human body. But to create a Google Map-like human atlas, a crosswalk table is needed to map the information on the ASCT+B table to highly detailed images of the human body. 
The images are in the SVG format for two reasons: it is scalable, and each element of the image can be referred to with an id. The crosswalk table then will map between the components in the ASCT+B table and these IDs in the SVG images.
As a starting point, we will focus on three anatomical structures: kidneys’ glomeruli, lungs’ alveoli, and colon’s crypts. 

## Crosswalk Table Format

The tables consist of six columns:
1. svg_id: describes the IDs of each AS/CT object on the SVG image files
2. label: describes the name in the UBERON (for AS) and CL (for CT) ontologies
3. OntologyID: describes the IDs of the UBERON (for AS) and CL (for CT) ontologies
4. representation_of: describes the PURL of the UBERON (for AS) and CL (for CT) ontologies
5. exist_asctb: the value is 1 if the object has been registered in the ASCT+B table, and 0 if the object has not been registered
6. type: AS if the object is an anatomical structure, and CT if the object is a cell type

## Renal Corpuscle

The crosswalk table of renal corpuscle is available on: https://raw.githubusercontent.com/fauzanmursyid/asctb-ftu-mapping/main/renal_corpuscle.csv
Some anatomical structures were not represented by any object in the original SVG image. For example, Bowman's space is a space between the visceral and parietal layers, so there was no ID from the SVG image to represent this AS. As the solution, we created a transparent path in the SVG file to represent this space. Here are the list of added paths on the SVG files:
1. path4883 represents Bowman's space
2. path17383 represents extraglomerular mesangium

The original SVG file is: https://raw.githubusercontent.com/fauzanmursyid/asctb-ftu-mapping/main/Schematics_Renal%20Corpuscle%20-%20human.svg
And the edited version is: https://raw.githubusercontent.com/fauzanmursyid/asctb-ftu-mapping/main/Schematics_Renal%20Corpuscle%20-%20human_edited.svg
