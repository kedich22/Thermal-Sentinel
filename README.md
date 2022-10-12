[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/kedich22/Thermal-Sentinel/main?labpath=Test%20burnscar.ipynb)
# Tool for visualization of lava flows/burnfires/themral activity on the land surface
&#8595 &#8595 *The more advanced version with burnfire visualization and exporting images is presented below, the link could be find at the bottom of this tutorial* &#8595 &#8595
Enhanced visualization of thermal hotspots based on Sentinel-2 imagery

### How to use it?
1. The tool could be used in 2 ways: **on your local server** and through the **binder deployed application**. I strongly advise you to choose the second option.
If you still want to use it on your local computer in the file `requerements.txt` all used Python packages with their versions that should be installed in your python environment, the `runtime.txt` contains the used version of Python.
2. In the Binder-deployed application all packages are already installed and all data could be retrieved online.

### The tutorial
1. During the first access to the application you should authorize yourself through the Jupyter Notebook. Unfortunately, at this point, I have not managed how to include this part directly to GUI. 
2. Click on the binder badge at the top of the README file or [click here](https://mybinder.org/v2/gh/kedich22/Thermal-Sentinel/main?labpath=Test%20burnscar.ipynb) to load the Jupyter Notebook. It might take some time to load the page (up to several minutes) due to the rendering process.
3. After the page is loaded if you are accessing the app for the first time you should authenticate yorself with Earth Engine to provide the access to this Notebook. For this purpose, your account should be already activated through the Google Earth Engine platform. 
Run the first chunk of code &rarr; follow the link &rarr; click "Generate Token" &rarr; Choose your Google account &rarr There will be a notification that Google has not verified this app, click `Continue` &rarr grant the access by ticking both boxes &rarr; copy the provided authorization code into the field in Jupyter Notebook and press enter &rarr; Congratulation! You are successfully authorized and could use the app!

![auth](https://user-images.githubusercontent.com/70434411/183929591-2a1d9d6f-62eb-422f-b38f-63e3e444988e.png)
![auth_token](https://user-images.githubusercontent.com/70434411/183929684-a87aa178-820b-46c1-9011-e2248fdc84e9.png)

4. After clicking on the viola rendering icon and wait until the application is rendered. After it is finally deployed and ready to use!
![voila](https://user-images.githubusercontent.com/70434411/183935707-ced0268c-56fb-4f51-b69b-fefe47df5190.png)

The follwoing screen will be opened:
![application](https://user-images.githubusercontent.com/70434411/186253616-70241bf0-02c5-438c-819f-9721d2dbb185.png)

1. `Select the area of interest` Firstly you need to specify the area of interest (AOI) via inidicating the ccordinates and buffer area, or you could click the checkbox `User-defined AOI` and draw manually the area on the map. It is not recommended to make an area large as the application is using only one sateelite image and the part of the area will not be covered by the resulting visualization. 
2. 'Select the date range` After the area is specified, please indicate the period of interest (I recemmend not to exceed the scale of several monnth to reduce computation time).
3. Click the button `List images` to list below all the existing dates with imagery that could be further visualizaed. Also you could `Clear fields` just by clicking one button and put them to default. After the area is chosen manually I recommend to click on the bin at the left map bar after `List images` is clicked to clean user drawings so not to overlap with the image (the polygon is saved and there no need to keep it there, if you want to reset and draw a new one click `Clear map` or just draw a new one, the old one will be rewritten).
4. If everything is selected properly, after a while the list with dates should appear below the `List images` button. You should select the date of interest and put the selected number in the field below `Select the image` and click `Submit`. After that the phrase `The image is selected` will appear below. Now you succesfully selected the image to visualize.
---
5. The next step is the visualization. The parameters are adjusted via the menu below the map.
You should specify 2 band combinations and their opacity on the first step. `Select the band combination` from the dropdown menu and set an opacity that will be associated with this layer. Two layers will be blended for visualization, so the background will mix two visualizations in one. If you want to show only one band combination just set the opacity slider at 0 for one of the layers.
Options for visualization (by Pierre Markuse, [click here](https://pierre-markuse.net/2018/04/30/visualizing-wildfires-burn-scars-sentinel-hub-eo-browser/)
- *Natural Colors* - A simple natural color band combination
- *Enhanced Natural Colors* - Natural colors with some NIR mixed in, especially to get better greens for vegetation
- *Natural NIR SWIR Mix* - A mix of natural and NIR/SWIR bands, usually quite pleasing visually and showing burn scars
- *NIR SWIR Colors 1* - A classic NIR/SWIR combination, very green vegetation, very red burn scars
- *NIR SWIR Colors 2* - Similar to the first one, colors are a bit more subtle with better smoke penetration
- *NIR SWIR Colors 3* - Very red and punchy combination, give it a try.
- *NIR SWIR Colors 4* - Good atmospheric penetration, somewhat visible burn scars and nicely highlighted hot spots
- *False Color* - Classic NIR false color image
- *Nat False Color* - NIR false color image with a natural-color-like appearance
- *Vegetation* - Useful to show healthy vegetation
- *Pan Band* - Monochrome B08 image

`Stretch min` and `Stretch max` is responsible for adjusting the lightness of the resulting image. 

With `Saturation` you could adjust the vividness of the image, if set to 0, the monochrome version will be resulted.

`Fire sensitivity` defines the sensitivity of hot spot setection. If you want to visualize more hotspot areas increase the number (but be aware of false postives). 1 is default and tested to work rather "well".

Next line allows user to `adjust` manually RGB visualization of the image. It's a "cheat" option to highlight something if you want to change the appearence of the image. You could add by defining positive values or substract by definine negative ones.

By `cropping and visualization` the choice how to present the visualization on the map could be done: to clip to the polygon of interest or to show the full image.

The final visualization parameters are `max` and `min`. It is Earth Engine visualization stretching. You could set the same values as in stretching above.

## The second version of the application to highlight burnscars + function to export the final image
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/kedich22/Thermal-Sentinel/main?labpath=Burnscar_forfires_new.ipynb)

The main difference with the previous version that this one is created nore to highlight burnfires. Added the visualization of burnscars. To set up the visualization change the parameter `Highlight` from 0. In addition in this version the export possibility is implemented.
[Cick here](https://mybinder.org/v2/gh/kedich22/Thermal-Sentinel/main?labpath=Burnscar_forfires_new.ipynb) to launch the application

And then in the section `Burnscar highlight` adjust the values:
- `Thsd low` Burnscar detection threshold low
- `Thsd high` Burnscar detection threshold high
- `Desat back` Burnscar desaturate backdrop
- `Darken back` Burnscar darken backdrop

Also in this version the feature to make a mosaic from images on the same date is added to cover the larger area.
This version also allows user to export the visualized image on the computer. The image is exported in tiff format, exported image contains three bands needed to provided visualization.
Firstly, select the path where to save the file. The image cannot be directly be saved on ypur computer. Firstly, it will appear in the environment, where the all online application files are stored. You could keep the default provided path: after click `Change`. 
In order to export the image after the path has been chosen click `Export image`. 
The image will appear on the left panel: the you have to left click on it and at this step to choose where to save it on your local computer:
![image](https://user-images.githubusercontent.com/70434411/195396364-aa5e0299-d02e-4fce-bd8a-071099a8e5c0.png)
### To do list
- [ ] Fix the moment with visualization of AOI polygon
- [x] Add image mosiacking to display larger areas
- [x] Add Burnscar visualization for burnfires
- [x] Make a version for burnfires
- [ ] Add the information while selecting images about the cloud cover in the AOI



