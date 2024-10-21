¨Layer 1¨
- Study Area: Segovia
- Looking for Livestock routes in Segovia
- Process(s): Clipping by mask layer for livestock routes
- Layer data installed through: https://idecyl.jcyl.es/geonetwork/srv/spa/catalog.search#/metadata/SPAGOBCYLMNADTSAMVPE

 ```python
processing.run("gdal:clipvectorbypolygon", {'INPUT':'C:\\Users\\localuser\\Downloads\\znie_cyl_vvpp_ejes.gpkg|layername=znie_cyl_vvpp_ejes','MASK':'C:/Users/localuser/Documents/GIS data/sg_province.gpkg|layername=prov_cyl_recintos','OPTIONS':'','OUTPUT':'TEMPORARY_OUTPUT'})
  ```

¨Layer 2¨
- Study Area: Segovia
- Looking for Types of Land in Segovia
- Process(s): Clipping by mask layer for types of land
- Layer data installed through: https://idecyl.jcyl.es/geonetwork/srv/spa/catalog.search#/metadata/SPAGOBCYLCITDTSLUCLA

```python
 processing.run("gdal:clipvectorbypolygon", {'INPUT':'C:\\Users\\localuser\\Downloads\\siu_cyl_clasue.gpkg|layername=siu_cyl_clasue','MASK':'C:/Users/localuser/Documents/GIS data/sg_province.gpkg|layername=prov_cyl_recintos','OPTIONS':'','OUTPUT':'TEMPORARY_OUTPUT'})
  ```

¨Layer 3¨
- Study Area: Segovia
- Looking for position points of Microtus arvalis
- Process(s): vector clipped by mask layer the Microtus arvalis position points
- Layer data installed through: Given by professor on previous session

```python
processing.run("gdal:clipvectorbypolygon", {'INPUT':'C:/Users/localuser/Documents/GIS data/Microtus_arvalis_5_!_bio1.gpkg|layername=bio1','MASK':'C:/Users/localuser/Documents/GIS data/sg_province.gpkg|layername=prov_cyl_recintos','OPTIONS':'','OUTPUT':'TEMPORARY_OUTPUT'})
  ```

¨Layer 4¨
- Study Area: Segovia
- Looking for protection zones for birds and power lines
- Process(s): vector clipped by mask layer of the protection zones for birds and power lines
- Layer data installed through: https://idecyl.jcyl.es/geonetwork/srv/spa/catalog.search#/metadata/SPAGOBCYLMNADTSAMZPA

```Python
processing.run("gdal:clipvectorbypolygon", {'INPUT':'C:/Users/localuser/Downloads/avifau_cyl_prot_laat.gpkg|layername=avifau_cyl_prot_laat','MASK':'C:/Users/localuser/Documents/GIS data/sg_province.gpkg|layername=prov_cyl_recintos','OPTIONS':'','OUTPUT':'C:/Users/localuser/Documents/GIS data/ZEPA sego.gpkg'})
  ```


¨Layer 5¨
- Study Area: Segovia
- Looking for the vulnerability of forest formations
- Process(s): vector clipped by mask layer of the vulnerability of tree formaiton in Segovia
- Layer data installed through:https://idecyl.jcyl.es/geonetwork/srv/spa/catalog.search#/metadata/SPAGOBCYLMNADTSAMFFV

```python
processing.run("gdal:clipvectorbypolygon", {'INPUT':'C:\\Users\\localuser\\Downloads\\formaciones_forestales_cyl_vulnerabilidad.gpkg|layername=formaciones_forestales_cyl_vulnerabilidad','MASK':'C:/Users/localuser/Documents/GIS data/sg_province.gpkg|layername=prov_cyl_recintos','OPTIONS':'','OUTPUT':'TEMPORARY_OUTPUT'})
  ```
