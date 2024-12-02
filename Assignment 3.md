# Layers
1. Occurrence of the animal species called Crocidua russula: Common microorganisms in Castilla y Leon
* Source: https://www.gbif.org/zh/occurrence/download?country=ES&taxon_key=2435654
* Layer Name: Crocidua_russula_occurrence
* Layer Type: CSV
* Scale: Castilla y Leon

2. Ocurrence of the animal species called Neomys anomalus: Common microorganims in Castilla y Leon
* Source: https://www.gbif.org/zh/occurrence/download?country=ES&taxon_key=7825895&year=2024,2024
* Layer Name: Neomys_anomalus_occurrence
* Layer Type: CSV
* Scale: Castilla y Leon

3. Ocurrence of the animal species called Apodemos sylvaticus: Common microorganims in Castilla y Leon
* Source: https://www.gbif.org/zh/occurrence/download?country=ES&taxon_key=2437760&year=2024,2024
* Layer Name: Apodemus_sylvaticus_occurrence
* Layer Type: CSV
* Scale: Castilla y Leon

4. Ocurrence of the animal species called Mus musculas: Common microorganims in Castilla y Leon
* Source: https://www.gbif.org/zh/occurrence/download?country=ES&taxon_key=7429082&year=2024,2024
* Layer Name: Mus_musculus_occurrence
* Layer Type: CSV
* Scale: Castila y Leon

5. Ocurrence of the animal species called Mus spretus: Common microorganims in Castilla y Leon
* Source: https://www.gbif.org/zh/occurrence/download?country=ES&taxon_key=2438793&year=2024,2024
* Layer Name: Mus_spretus_occurrence
* Layer Type: CSV
* Scale: Castilla y Leon

6. Ocurrence of the animal species called Rattus norvegicus: Common microorganims in Castilla y Leon
* Source: https://www.gbif.org/zh/occurrence/download?country=ES&taxon_key=2439261&year=2024,2024
* Layer Name: Rattus_norvegicus_occurrence
* Layer Type: CSV
* Scale: Castilla y Leon

7. Ocurrence of the animal species called Eliomys quercinus: Common microorganims in Castilla y Leon
* Source: https://www.gbif.org/zh/occurrence/download?country=ES&taxon_key=2439683&year=2024,2024
* Layer Name: Eliomys_quercinus_occurrence
* Layer Type: CSV
* Scale: Castilla y Leon


# Spatial Analysis Plans
1. 
  a. Purpose
  * My first spatial analysis plan is focusing on finding the distribution of the previous mentioned species throughout the region of Castilla y Leon. On one of our field trips we obtained the data that this species were commonly found in the region, along with the common vole. Therefore, the reason I focused on finding their distribution is to see if they live near the vole as well as to see if there is any possible correlation to where they live with where the common vole lives.

b. Tools & Workflows
* To accompish these, the following steps were done:
    1. Download all CSV files from this following website called GBIF: https://www.gbif.org/
    2. Once it is downloaded, I will extract them from the zip file and put them on a specific folder
    3. All this data will then be put into my virtual computer QGIS
    4. Now we go to Processing Tool and select Create Points Layer from Table
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
    6. Lastly, to make it just for the Castilla y Leon region we need to, we select Clip Vector by Mask Layer from Vector Geoprocessing
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
    8. At the end I will have the distributions of the animal species throughout Castilla y Leon
 
c. Expected Outcome
* The expected outcome for this analysis is to

2. 
  a. Purpose
  * For my second spatial analysis the plan is to create buffers of all the microorganisms in relation to the common vole. By having buffers with radius that go according to each and one of their home ranges which varied according to the species we are able to see if their habitat range overlaps with the living range of the common vole. Knowing these information helps on seeing if the solutions that we propose to tackle the plague will have an impact on the habitat or the non-target animals. Through this information we will now know which areas have higher diversity population and apply the solution according to the possible impact it might have on other organisms.

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
  * 


# Cartographic
* Topic & Intended Message
  
* Map
![Map Showing Relation of Microorganism with Vole](Cartography Map.Assignment3.png)
