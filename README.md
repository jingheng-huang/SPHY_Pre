# SPHY_Pretools_basic - Tools to get  input for SPHY

* Copy this dir to QGIS plugin dir, the add this tool to QGIS, this is a GUI which is easy to use.

* All input should be indicated in panj.cfg file. You can also use the GUI to initialize the file.

## The database of the whole Tibetan plateau can be download from ...

## Some important tips 

* if you use version 3, you need use the glacier input prepare tool to get the input.

* -----------------------[Soil] 
The sub-sat-soil map in the database has some Abnormal values near Tien Shan. which must need to use the condition analysis to get rid of those values. 

* -----------------------[Route]
Outlets should be created after the river network
In basin delineation process. If the basin boundary is not correct, try:

1. Move the outlets to the river network (The river network will be generated automatically by the preProcessor) 
2. If not work, then changing the resolution, no need to exactly int like 1000, 500 or *** **
3. Do not choose too wide extent, otherwise you will get wrong basin boundary!

* -----------------------[forcing]
The code was modified to recognized one nc file for each forcing type, eg.g precipitation

Temperature Forcing files must starts with Tair Tmax Tmin Prcp.  e.g Tamx.nc Tmin.nc 

Make sure the units is mm for precipitation, and Degrees Celsius for temperature !! if not, change the code in forcing.py.
   
Only accept the tiff input for the dem. Since the process of converting NC to tiff would has some problem if you use the old gdal version in the QGIS. 

* -----------------------[Glacier]
Must be clip to the extent