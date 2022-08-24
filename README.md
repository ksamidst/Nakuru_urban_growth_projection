_____________INTRODUCTION_____________<br/>

This work is part of project MIDST; (Monitoring for Information and Decisions using Space Technologies) piloted by the Kenya Space Agency (KSA),
in collaboration with a team from other government institutions. It is part of a subproject Spatial Planning and Urbanization, conducted in the Nakuru municipality area. This code allows users to run an urban growth prediction algorithm applying the cellular automata technique. Using the datasets provided in this repository as guided in the script file 'code.py', you will be able to generate an image/ map of the Nakuru area showing what the Land use would look like in the year 2030.

______________RUNNING THE SCRIPT______________<br/>

This process will consist of four steps as follows:<br/>
1.) Downloading the files<br/>
2.) Loading the data onto QGIS platform
3.) Loading and running the python script on QGIS<br/>

_______________1.) DOWNLOADING THE FILES____________________<br/>
![image](https://user-images.githubusercontent.com/75077556/186348151-fcfe52d3-bc00-47e6-ad67-59fecc4df433.png)<br/>
Click on the 'Clone' button at the top of this page, then click on 'Download ZIP', as shown in the image above. Once the zipped file is downloaded, 
extract the files to a location of your choice. You can open the folders to view the files. There are a number of different files in the folder; 
there is the script file 'code.py' containing the python code. The other files, particularly the GeoTIFF images serve as inputs to the algorithm in the script file. These files, their descriptions and purpose are as shown below:
1) The Land Use Land Cover images:
- Actual_1989.tif: 1989 Land cover image of Nakuru municipality
- Actual_2000.tif: 2000 Land cover image of Nakuru municipality
- Actual_2010.tif: 2010 Land cover image of Nakuru municipality
- Actual_2020.tif: 2020 Land cover image of Nakuru municipality
2) Population density:
- den1989.tif: Population density in 1989
- den1999.tif: Population density in 1999
- den2000.tif: Population density in 2000
- den2009.tif: Population density in 2009
- den2010.tif: Population density in 2010
- den2019.tif: Population density in 2019
- den2020.tif: Population density in 2020
- den2029.tif: Population density in 2029
- den2030.tif: Population density in 2030
3) Government restricted areas:
- dda_2021_government_restricted_2.tif
4) Slope:
- slope.tif
5) Distribution of roads:
- roaddist.tif


_______________2.) LOADING THE DATA ONTO QGIS PLATFORM________________<br/>
Once you have downloaded the data, you can visualize th data using the [QGIS software](https://www.qgis.org/en/site/forusers/download.html). Ensure you
have the software installed for your platform; Windows/ Linux/ MacOS/ BSD. The data you have downloaded includes a collection of files including GeoTIFF
image files. Once you have QGIS up and running on your machine, you can load and visualize the GeoTIFF files using the 'Layer' menu as shown in the image below.<br/>
![image](https://user-images.githubusercontent.com/75077556/186357634-1bbe1f30-ccf5-47c0-af9a-3f14ecdab642.png)<br/>
In the 'Data Source Manager' dialog box that pops up, use the three dots button shown on the right to navigate to the location of the GeoTIFF files you have downloaded
and want to display, as shown in the image below.
![image](https://user-images.githubusercontent.com/75077556/186360091-c2959a89-d4cc-466a-b86d-fbf12bdef0ae.png)<br/>
Once you have selected the image you want to visualize, click on the 'Add' button highlighted in the image above, then click close. You will see a gray scale image as shown in the image below with distinctive classes represented in different shades as shown in the image below. 
![image](https://user-images.githubusercontent.com/75077556/186364410-39c5167a-bd31-416f-8b76-3370a9da4a25.png)<br/>
As shown in the image above in the 'Layers' side menu, it is possible to add several layers. To change the visualization properties of the image, double click on the layer whose properties you want to modify. A 'Layer Properties' dialog box will appear as shown in the image below.
![image](https://user-images.githubusercontent.com/75077556/186365183-d94fe4f2-64d9-486b-845c-0df41ca165aa.png)<br/>
For a finite number of distinct classes with different pixel values, it is recommended that you select 'Paletted/ Unique Values' option under render type as shown in the image above, then click classify. You may select different colors for different classes represented by their pixel values as shown in the window.<br/>
For this case; the Nakuru municipality classified image, the images have seven distinct classes with their corresponding pixel values as shown below.
- Pixel value 1: Built-Up areas.
- Pixel value 2: Forest areas.
- Pixel value 3: Grassland areas.
- Pixel value 4: Wetland areas.
- Pixel value 5: Cropland areas.
- Pixel value 6: Bareland areas.
- Pixel value 7: Rocky areas.

_______________3.) LOADING AND RUNNING THE PYTHON SCRIPT ON QGIS________________<br/>
The algorithm that generates the projected urbanization product is implemented as a python script. You need to run this python script in a python environment to generate the product. The QGIS platform offers a python environment for executing programs especially for remote sensing functions. To load and run the python script on QGIS, on the 'Plugins' menu, click on python console as shown on the image below.<br/>
![image](https://user-images.githubusercontent.com/75077556/186376398-8da9a0a0-4ef2-4a2c-bd29-888fd3d6f7a5.png)<br/>
The python console window will appear as shown in the image below. To open the python editor, click on the 'show editor' icon as highlighted in the image. You need to load the script 'code.py' onto this editor. To do this, click on the 'Open script...' icon on the top of the editor and navigate to the location of 'code.py'.<br/>
![image](https://user-images.githubusercontent.com/75077556/186386833-9bd70649-0d56-42a9-b964-27016c962632.png)<br/>
Python script is displayed on the editor. Before you can run the script to view the output, you need to make one modification to it. Locate the line of code that specifies the location of the files you are working with.<br/>
![image](https://user-images.githubusercontent.com/75077556/186390235-09227cdd-3a22-49e4-a0f9-2b5aa08b28c2.png)<br/>
Change this value to the location of the files on your computer. Once you run the script, it will generate the result image in the same location of the files you are working with, with the file name 'NEW_predictedlandcover_ra_30m_2030N.tif' as indicated in the script. Load this image as a layer on QGIS to visualize it.
