
# Description and Process
1. Finding of Map
    * When looking for a map I found one that focused on how the wildlife of Spain was impacted due to use of poisonous products such as rondeticides. This ended up being perfect because one of our solutions is the use of biorodenticide so if we know where the wildlife is being affected, we can maybe try to do testing or the introduction of it. However, an issue I found was that the map was of whole Spain, and I wanted to solely focus on Castilla y Leon. Therefore, when taking the screenshot, I primarly focused it on that area.
     * The name of the article I found was: Intoxicaciones intencionadas y accidentales de fauna silvetre y domestica en España: diferentcias entre Comunidades Autonomas
       * Link: https://www.redalyc.org/pdf/919/91925068006.pdf
2. Georeferencing
     * Started by taking the screenshot through Snipping tool, and then saving it through the Paint app as a .tif file.
     * The .tif file was then added to GIS, as well as it was added to the Map Canvas.
     * Here, reference points were added to the area surrounding Castilla y Leon.
     * The file, was then saved and was added to the GIS.
3. Digitalizing the Data
     * A new geopackage layer was added where certain features were determined, which are the following:
         * Coordinate Reference System: EPSG: 25830 - ETRS89 / UTM zone 30N
         * Geometry Type: Point
         * New Field Name: press_abs
         * New Field Type: 123 Integer (32 Bites)
      * A field list was then added, and I pressed okay, to create the new layer.
      * Once this was done, I needed to create two types of points by pressing Toogle Editing:
         * The first set of points were the ¨Positive: 1¨ which showed that there was a high intoxication levels on the wildlife. 
         * The second set of points were the ¨Negative: 0¨ which showed that there was no intoxication levels on the wildlife, but were found dead due to other reasons.
         * Negative: 0
      * Once I plugged the first set of points I pressed the attribute table, where I changed it to press_abs and put 1
      * I did the same procedure for the second set of points and put the value of 0.
      * Once all of these was done, I went to symbology where I changed it to categorized and added the colors of blue being 1 and red being 0.

# Information Used
  * Point File: 
