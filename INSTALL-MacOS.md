# VISE Installation Instructions for Mac OS

### Step 1 : Install Docker
 Download [Docker-CE for MacOS](https://store.docker.com/editions/community/docker-ce-desktop-mac) 
 and install the Docker application. The [installation instructions](hhttps://docs.docker.com/docker-for-mac/install/) 
 provide more details about the installation process.
 
 The VISE Docker image has been built using **docker version 17.06.0**. 
 Please ensure that you install the same (or superior) version of Docker in your 
 computer.
 
 The VISE application requires access to your local disk to store application 
 data and load the training images. Start Docker, click on the Docker icon in
 the status bar (top right corner), click *Preferences* and in *File Sharing* 
 menu (on the top), ensure that `/Users` is added to the list as shown below:

 <img src="docs/help/kitematic/macos/Docker_preferences.png" width="300"/> 
 <img src="docs/help/kitematic/macos/Docker_preferences_file_sharing.png" width="300"/>
 
### Step 2 : Install and Open Kitematic
 [Kitematic](https://kitematic.com/) is a tool that provides a graphical user 
 interface to load, start, stop and configure Docker 'containers' (analogous to applications).
 Click on the Docker icon in the status bar (top right corner) and click *Kitematic* to 
 download and install Kitematic for MacOS. Alternatively, you can [download and 
 install](https://www.docker.com/products/docker-toolbox) Kitematic as part of Docker Toolbox.
 
 Once this tool is installed, click on the Docker icon in the status bar (top 
 right corner) and click *Kitematic*.

### Step 3 : Install oxvgg/vise
 In the Kitematic tool, enter **oxvgg** in the search toolbar. This will 
 show all the Docker containers released by the Visual Geometry Group (VGG) as 
 shown below:
 
 <img src="docs/help/kitematic/macos/Kitematic_search_oxvgg.png" width="400"/>
 
 Click **Create** button in the bottom right corner of the box panel corresponding 
 to VISE. This will download  the VISE container (it may take a few minutes).
 
 <img src="docs/help/kitematic/macos/Kitematic_downloading_image_vise.png" width="400"/>
 
 After the download is complete, the VISE container will start automatically as 
 shown below :
 
 <img src="docs/help/kitematic/macos/Kitematic_vise_first_run.png" width="400"/>
 
### Step 4 : Configure ports and volume
Ensure that the VISE container is running (*RUNNING* will appear in the top side of 
kitematic window, if not, press the *START* button). Click **Settings** (near 
top-right corner) and click on **Hostname / Ports** tab to show the port 
configuration panel. Edit and **Save** the published port so that the docker 
port `9971` maps to `localhost:9971` and port `9973` maps to `localhost:9973`.
Don't forget to press **Save** after you update the ports.

 <img src="docs/help/kitematic/macos/Kitematic_vise_configure_ports.png" width="400"/>
 
Click the **Volumes** panel to show the Configure Volumes panel. The VISE 
application uses the following two folders:
 * `/opt/ox/vgg/vise/application_data` : This is the folder where VISE stores all its internal application files
 * `/opt/ox/vgg/mydata/images` : This is the folder where user will be asked to copy their personal images that needs to be indexed and made searchable

As a user, you can map these Docker folders (which are ordinarily invisible in the Mac Finder)
to any local folder in your computer.
For this guide, we assume that you configure volumes as shown below:

 <img src="docs/help/kitematic/macos/Kitematic_vise_configure_volumes.png" width="400"/>

### Step 5 : Run oxvgg/vise
Press **Stop** followed by **Start** to restart the container. Now visit 
[http://localhost:9971](http://localhost:9971) in a web browser and follow 
the [User Guide](UserGuide.md) to train VISE for searching your own image collections.

Ensure that your Kitematic tool shows something similar to the screenshot below:

 <img src="docs/help/kitematic/macos/Kitematic_vise_running.png" width="400"/>

### Step 6 : Stopping oxvgg/vise
In the Kitematic tool, click on **oxvgg/vise** on left hand side panel and 
press **Stop** button to stop the VISE container.
