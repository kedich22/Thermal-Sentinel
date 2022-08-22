[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/kedich22/Thermal-Sentinel/main?labpath=Test%20burnscar.ipynb)
# Tool for visualization of lava flows/burnfires/themral activity om the land surface
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
