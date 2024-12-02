# Layers
1. Occurrence of the animal species called Crocidua russula: Common microorganisms in Castilla y Leon
* Source: https://www.gbif.org/zh/occurrence/download?country=ES&taxon_key=2435654
* Layer Name: Crocidua_russula_occurrence
* Layer Type: CSV
* Scale: Castilla y Leon

2. Occurrence of the animal species called Neomys anomalus: Common microorganisms in Castilla y Leon
* Source: https://www.gbif.org/zh/occurrence/download?country=ES&taxon_key=7825895&year=2024,2024
* Layer Name: Neomys_anomalus_occurrence
* Layer Type: CSV
* Scale: Castilla y Leon

3. Occurrence of the animal species called Apodemos sylvaticus: Common microorganisms in Castilla y Leon
* Source: https://www.gbif.org/zh/occurrence/download?country=ES&taxon_key=2437760&year=2024,2024
* Layer Name: Apodemus_sylvaticus_occurrence
* Layer Type: CSV
* Scale: Castilla y Leon

4. Occurrence of the animal species called Mus musculas: Common microorgansims in Castilla y Leon
* Source: https://www.gbif.org/zh/occurrence/download?country=ES&taxon_key=7429082&year=2024,2024
* Layer Name: Mus_musculus_occurrence
* Layer Type: CSV
* Scale: Castila y Leon

5. Occurrence of the animal species called Mus spretus: Common microorganims in Castilla y Leon
* Source: https://www.gbif.org/zh/occurrence/download?country=ES&taxon_key=2438793&year=2024,2024
* Layer Name: Mus_spretus_occurrence
* Layer Type: CSV
* Scale: Castilla y Leon

6. Occurrence of the animal species called Rattus norvegicus: Common microorganisms in Castilla y Leon
* Source: https://www.gbif.org/zh/occurrence/download?country=ES&taxon_key=2439261&year=2024,2024
* Layer Name: Rattus_norvegicus_occurrence
* Layer Type: CSV
* Scale: Castilla y Leon

7. Occurrence of the animal species called Eliomys quercinus: Common microorganisms in Castilla y Leon
* Source: https://www.gbif.org/zh/occurrence/download?country=ES&taxon_key=2439683&year=2024,2024
* Layer Name: Eliomys_quercinus_occurrence
* Layer Type: CSV
* Scale: Castilla y Leon

# Relevance of Layers
  * These layers are relevant to our group's question of how the proposed solutions that we have such as the sonometers, bio-rodenticide, biological control, etc will possibly affect other major microorganisms that live in Castilla y Leon. Therefore, to answer the following question, the chosen layers are maps of occurrence of significant animals that one might find in the region. So, understanding the possible relation or sharing of habitat that those animals might have with the common vole will help us understand how to apply our solutions and where specifically.

# Spatial Analysis Plans
1. 
  a. Purpose
  * My first spatial analysis plan is focused on finding the distribution of the previously mentioned species throughout the region of Castilla y Leon. On one of our field trips we obtained the data that this species were commonly found in the region, along with the common vole. Therefore, the reason I focused on finding their distribution is to see if they live near the vole as well as to see if there is any possible correlation to where they live with where the common vole lives.

b. Tools & Workflows
* To accompish these, the following steps were done:
    1. Download all CSV files from the following website called GBIF: https://www.gbif.org/
    2. Once it is downloaded, I extracted them from the zip file and put them on a specific folder
    3. All this data was then put into my virtual computer QGIS
    4. Now we press Processing Tool and select Create Points Layer from Table
       * Running Process for each species:
           * Crocidua russula
             ```
              processing.run("native:createpointslayerfromtable", {'INPUT':'C:/Users/localuser/Documents/Assignment_3_Final/Crocidua_russula_occurrence .csv','XFIELD':'decimalLongitude','YFIELD':'decimalLatitude','ZFIELD':'','MFIELD':'','TARGET_CRS':QgsCoordinateReferenceSystem('EPSG:4326'),'OUTPUT':'TEMPORARY_OUTPUT'})
             ```
            * Neomys anomalus
              ```
               processing.run("native:createpointslayerfromtable", {'INPUT':'C:/Users/localuser/Documents/Assignment_3_Final/Neomys_anomalus_occurrence .csv','XFIELD':'decimalLongitude','YFIELD':'decimalLatitude','ZFIELD':'','MFIELD':'','TARGET_CRS':QgsCoordinateReferenceSystem('EPSG:4326'),'OUTPUT':'TEMPORARY_OUTPUT'})
              ```
            * Apodemos sylvaticus
              ```
              processing.run("native:createpointslayerfromtable", {'INPUT':'C:/Users/localuser/Documents/Assignment_3_Final/Apodemus_sylvaticus_occurrence.csv','XFIELD':'decimalLongitude','YFIELD':'decimalLatitude','ZFIELD':'','MFIELD':'','TARGET_CRS':QgsCoordinateReferenceSystem('EPSG:4326'),'OUTPUT':'TEMPORARY_OUTPUT'})
              ```
            * Mus musculas
              ```
               processing.run("native:createpointslayerfromtable", {'INPUT':'C:/Users/localuser/Documents/Assignment_3_Final/Mus_musculus_occurrence.csv','XFIELD':'decimalLongitude','YFIELD':'decimalLatitude','ZFIELD':'','MFIELD':'','TARGET_CRS':QgsCoordinateReferenceSystem('EPSG:4326'),'OUTPUT':'TEMPORARY_OUTPUT'})
              ```
            * Mus spretus
              ```
               processing.run("native:createpointslayerfromtable", {'INPUT':'C:/Users/localuser/Documents/Assignment_3_Final/Mus_spretus_occurrence.csv','XFIELD':'decimalLongitude','YFIELD':'decimalLatitude','ZFIELD':'','MFIELD':'','TARGET_CRS':QgsCoordinateReferenceSystem('EPSG:4326'),'OUTPUT':'TEMPORARY_OUTPUT'})
              ```
            * Rattus norvegicus
              ```
               processing.run("native:createpointslayerfromtable", {'INPUT':'C:/Users/localuser/Documents/Assignment_3_Final/Rattus_norvegicus_occurrence.csv','XFIELD':'decimalLongitude','YFIELD':'decimalLatitude','ZFIELD':'','MFIELD':'','TARGET_CRS':QgsCoordinateReferenceSystem('EPSG:4326'),'OUTPUT':'TEMPORARY_OUTPUT'})
              ```
            * Eliomys quercinus
              ```
               processing.run("native:createpointslayerfromtable", {'INPUT':'C:/Users/localuser/Documents/Assignment_3_Final/Eliomys_quercinus_occurrence.csv','XFIELD':'decimalLongitude','YFIELD':'decimalLatitude','ZFIELD':'','MFIELD':'','TARGET_CRS':QgsCoordinateReferenceSystem('EPSG:4326'),'OUTPUT':'TEMPORARY_OUTPUT'})
              ```
    6. Lastly, to make it just for the Castilla y Leon region we select Clip Vector by Mask Layer from Vector Geoprocessing
       * Running Process for each species:
         * Crocidua russula
           ```
            processing.run("gdal:clipvectorbypolygon", {'INPUT':'C:/Users/localuser/Documents/Assignment_3_Final/Crocidua_russila-occurrence_pointlayer.gpkg|layername=crocidua_russula_points','MASK':'C:/Users/localuser/Documents/GIS data/prov_cyl_recintos.gpkg|layername=prov_cyl_recintos','OPTIONS':'','OUTPUT':'TEMPORARY_OUTPUT'})
           ```
          * Neomys anomalus
            ```
             processing.run("gdal:clipvectorbypolygon", {'INPUT':'C:/Users/localuser/Documents/Assignment_3_Final/Neomys_anomalus_occurrence_pointlayer-gpkg.gpkg|layername=points_from_table','MASK':'C:/Users/localuser/Documents/GIS data/prov_cyl_recintos.gpkg|layername=prov_cyl_recintos','OPTIONS':'','OUTPUT':'TEMPORARY_OUTPUT'})
            ```
          * Apodemos sylvaticus
            ```
            processing.run("gdal:clipvectorbypolygon", {'INPUT':'C:\\Users\\localuser\\Documents\\Assignment_3_Final\\Apodemus_sylvaticus_pointalyer.csv.gpkg|layername=apodemus_sylvaticus_points','MASK':'C:/Users/localuser/Documents/GIS data/prov_cyl_recintos.gpkg|layername=prov_cyl_recintos','OPTIONS':'','OUTPUT':'TEMPORARY_OUTPUT'})
            ```
          * Mus musculas
            ```
             processing.run("gdal:clipvectorbypolygon", {'INPUT':'C:\\Users\\localuser\\Documents\\Assignment_3_Final\\Mus_musculus_occurrence_pointalyer.csv.gpkg|layername=points_from_table','MASK':'C:/Users/localuser/Documents/GIS data/prov_cyl_recintos.gpkg|layername=prov_cyl_recintos','OPTIONS':'','OUTPUT':'TEMPORARY_OUTPUT'})
            ```
          * Mus spretus
            ```
            No points detected outside Castilla y Leon, so need to clip.
            ```
          * Rattus norvegicus
            ```
             processing.run("gdal:clipvectorbypolygon", {'INPUT':'C:\\Users\\localuser\\Documents\\Assignment_3_Final\\Rattus_norvegicus_occurrence_points.gpkg|layername=rattus_norvegicus_points_','MASK':'C:/Users/localuser/Documents/GIS data/prov_cyl_recintos.gpkg|layername=prov_cyl_recintos','OPTIONS':'','OUTPUT':'TEMPORARY_OUTPUT'})
            ```
          * Eliomys quercinus
            ```
             processing.run("gdal:clipvectorbypolygon", {'INPUT':'C:\\Users\\localuser\\Documents\\Assignment_3_Final\\Eliomys_quercinus_occurrence.points.gpkg|layername=eliomys_quercinus_points','MASK':'C:/Users/localuser/Documents/GIS data/prov_cyl_recintos.gpkg|layername=prov_cyl_recintos','OPTIONS':'','OUTPUT':'TEMPORARY_OUTPUT'})
            ```
    8. At the end I will have the distributions of the microorganisms in Castilla y Leon
 
c. Expected Outcome
* The expected outcome of this analysis is to show the microorganisms that live in Castilla y Leon along with the common vole. It is a safe assumption to believe that we will see many of the chosen animals living in the same areas, but one can also assume that there will be couple of animals that do not. When doing this, the outcome that we ended up achieving is that almost all of the microorganisms chosen are found in the region except for two which are the Mus spretus and the Rattus norvegicus. Even though we found information about those two living in Spain, there are no current records of them living in Castilla y Leon, or at least not recorded ones as seen on the map.

2. 
  a. Purpose
  * For my second spatial analysis the plan is to create buffers of all the microorganisms in relation to the common vole. By having buffers with radius that go according to each and one of their home ranges which vary according to the species we are able to see if their habitat range overlaps with the living range of the common vole. Knowing these information helps on see
analyze if the proposed solution to tackle the plague will have an impact on the habitat or the non-target animals. Through this information we will now know which areas have higher diversity population and apply the solution according to the possible impact it might have on other organisms.

  b. Tools & Workflows
  * To accomplish these, the following steps were added to the previous data that was achieved:
    1. Choose the clipped point layers of each species and press Reproject Layer
    2. Here, we change the CRS to EPSG 25830 - ETRS 84 / UTM Zone 30N
         * Running of Process for each species:
             * Crocidua russula
               ```
                 processing.run("native:reprojectlayer", {'INPUT':'C:\\Users\\localuser\\Documents\\Assignment_3_Final\\Crocidua_russila-occurrence_pointlayer_clipped.gpkg|layername=crocidua_russula_occurrence_clipped_mask','TARGET_CRS':QgsCoordinateReferenceSystem('EPSG:25830'),'CONVERT_CURVED_GEOMETRIES':False,'OPERATION':'+proj=pipeline +step +proj=unitconvert +xy_in=deg +xy_out=rad +step +proj=utm +zone=30 +ellps=GRS80','OUTPUT':'TEMPORARY_OUTPUT'})
               ```
              * Neomys anomalus
                ```
                 processing.run("native:reprojectlayer", {'INPUT':'C:\\Users\\localuser\\Documents\\Assignment_3_Final\\Neomys_anomalus_occurrence_pointlayer-gpkg.gpkg|layername=points_from_table','TARGET_CRS':QgsCoordinateReferenceSystem('EPSG:4326'),'CONVERT_CURVED_GEOMETRIES':False,'OPERATION':'+proj=noop','OUTPUT':'TEMPORARY_OUTPUT'})
                ```
              * Apodemos sylvaticus
                ```
                 processing.run("native:reprojectlayer", {'INPUT':'C:\\Users\\localuser\\Documents\\Assignment_3_Final\\Apodemus_sylvaticus_pointalyer_clipped.csv.gpkg|layername=apodemus_sylvaticus_occurrence_clipped','TARGET_CRS':QgsCoordinateReferenceSystem('EPSG:25830'),'CONVERT_CURVED_GEOMETRIES':False,'OPERATION':'+proj=pipeline +step +proj=unitconvert +xy_in=deg +xy_out=rad +step +proj=utm +zone=30 +ellps=GRS80','OUTPUT':'TEMPORARY_OUTPUT'})
                ```
              * Mus musculas
                ```
                 processing.run("native:reprojectlayer", {'INPUT':'C:\\Users\\localuser\\Documents\\Assignment_3_Final\\Mus_musculus_pointlayer_clipped.gpkg|layername=clipped_mask','TARGET_CRS':QgsCoordinateReferenceSystem('EPSG:25830'),'CONVERT_CURVED_GEOMETRIES':False,'OPERATION':'+proj=pipeline +step +proj=unitconvert +xy_in=deg +xy_out=rad +step +proj=utm +zone=30 +ellps=GRS80','OUTPUT':'TEMPORARY_OUTPUT'})
                ```
              * Eliomys quercinus
                ```
                 processing.run("native:reprojectlayer", {'INPUT':'C:\\Users\\localuser\\Documents\\Assignment_3_Final\\Eliomys_quercinus_occurrence_points_clipped.gpkg|layername=eliomys_quercinus_points_clipped','TARGET_CRS':QgsCoordinateReferenceSystem('EPSG:25830'),'CONVERT_CURVED_GEOMETRIES':False,'OPERATION':'+proj=pipeline +step +proj=unitconvert +xy_in=deg +xy_out=rad +step +proj=utm +zone=30 +ellps=GRS80','OUTPUT':'TEMPORARY_OUTPUT'})
                ```
               
    4. Then, we add the buffer layer by going to Vector Geometry, and pressing Buffersç
         * Running Process for each species:
           * Crocidua russula
             ```
              processing.run("native:buffer", {'INPUT':'C:\\Users\\localuser\\Documents\\Assignment_3_Final\\Crocidua_russula_reprojected.gpkg|layername=reprojected_crocidua_russula','DISTANCE':5000,'SEGMENTS':5,'END_CAP_STYLE':0,'JOIN_STYLE':0,'MITER_LIMIT':2,'DISSOLVE':False,'SEPARATE_DISJOINT':False,'OUTPUT':'TEMPORARY_OUTPUT'})
             ```
            * Neomys anomalus
              ```
               processing.run("native:buffer", {'INPUT':'C:\\Users\\localuser\\Documents\\Assignment_3_Final\\Neomy_anomalus_reprojected-gpkg.gpkg|layername=neomy_anomalus_reprojected','DISTANCE':3000,'SEGMENTS':5,'END_CAP_STYLE':0,'JOIN_STYLE':0,'MITER_LIMIT':2,'DISSOLVE':False,'SEPARATE_DISJOINT':False,'OUTPUT':'TEMPORARY_OUTPUT'})
              ```
            * Apodemos sylvaticus
              ```
               processing.run("native:buffer", {'INPUT':'C:\\Users\\localuser\\Documents\\Assignment_3_Final\\Apodemus_sylvaticus_reprojection.gpkg|layername=apodemus_sylvaticus_reproject','DISTANCE':5000,'SEGMENTS':5,'END_CAP_STYLE':0,'JOIN_STYLE':0,'MITER_LIMIT':2,'DISSOLVE':False,'SEPARATE_DISJOINT':False,'OUTPUT':'TEMPORARY_OUTPUT'})
              ```
            * Mus musculas
              ```
               processing.run("native:buffer", {'INPUT':'C:\\Users\\localuser\\Documents\\Assignment_3_Final\\Mus_musculus_reprojection.gpkg|layername=mus_musculus_reprojection','DISTANCE':3000,'SEGMENTS':5,'END_CAP_STYLE':0,'JOIN_STYLE':0,'MITER_LIMIT':2,'DISSOLVE':False,'SEPARATE_DISJOINT':False,'OUTPUT':'TEMPORARY_OUTPUT'})
              ```
            * Eliomys quercinus
              ```
               processing.run("native:buffer", {'INPUT':'C:\\Users\\localuser\\Documents\\Assignment_3_Final\\Eliomys_quercinus_reprojection_buffered-gpkg.gpkg|layername=eliomys_quercinus_reprojection','DISTANCE':5000,'SEGMENTS':5,'END_CAP_STYLE':0,'JOIN_STYLE':0,'MITER_LIMIT':2,'DISSOLVE':False,'SEPARATE_DISJOINT':False,'OUTPUT':'TEMPORARY_OUTPUT'})
              ```
              
    6. On the Buffers section, the distance is changed according to the microorganism and the distance is displayed in meters

  c. Expected Outcome
  * The expected outcome of this analysis is to show that there are some microorganisms animals that will overlap the habitat range of the common vole as the areas the common vole live in are also suitable for other species to live. At the same it will also show that some species will not overlap with the common vole giving a green light on the proceeding of the proposed solutions. Once again, when doing the testing, the resulsts showed both, that some do overlap and some do not, so when doing the project it is important to look at these areas.


# Cartographic
* Topic & Intended Message
  
  The topic and intended message the viewer should understand from the map is that the chosen microorganisms both do not and do overlap the common vole's habitat range. Some species have more distribution around Castilla y Leon as well as others do not, which makes one understand that the proposed solutions such as the appliance of bio-rodenticide, sonometers, etc are a viable options. Due to some areas not having great variety of diversity, but some areas do so more careness will be needed when doing the tests on those specific areas. The layers that were used were occurrence maps of the microorganisms, which are displayed as dots around the region. In addition, it also has buffers which displays what is around the area that the species lives in, displaying possible interactions with other beings or habitats. Each layer is styled in groups with the name of the species, and inside the group the squares are the buffers and the dots are the occurrence of the animal. The layout of the map is organized with a scale, an arrow to signal North, the legend to show what is being displayed, and the title to show what is the topic.
  
* Map
  
![Cartography Map.Assignment3.png](https://github.com/Pedro-Alvestegui/BESS-2024-24/blob/main/Cartography%20Map_Assignment3.png)
