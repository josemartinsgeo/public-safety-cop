﻿# Building the Sample Public Safety Common Operational Picture App

## Requirements

* Adobe Flash Builder with the 4.6 version of
[Adobe's Flex SDK](http://www.adobe.com/devnet/flex/flex-sdk-download.html).

* If you are using automatic builds,
    1. install Apache Ant 1.8.2 or later - [About](http://ant.apache.org/)
    2. set the path to the FlashBuilderC.exe command-line compiler in file flexbuild.bat

## How To Set Up for Builds

These steps set up a Flash Builder workspace for this project and then save it into a zip so that the
build process has fresh ingredients to fall back upon in the case of workspace corruption.

1. Download Esri's
[ArcGIS Viewer 3.0 for Flex source](https://github.com/ArcGIS/ArcGISViewerForFlex/archive/flexviewer-3.0-src.zip)
from GitHub

2. From the ArcGIS Viewer for Flex zip, extract its top-level folder ArcGISViewerForFlex-flexviewer-3.0-src
into your public-safety-cop folder; add two underscores to the front of its name so that git will ignore it;
discard the zip

3. Download Esri's
[ArcGIS API 3.0 for Flex](http://www.esri.com/apps/products/download/index.cfm?fuseaction=download.main&downloadid=801)
from Esri

4. From the ArcGIS API for Flex zip, extract the file ArcGIS_Flex\libs\agslib-3.0-2012-06-06.swc
into the __ArcGISViewerForFlex-flexviewer-3.0-src\libs folder; discard the zip

5. Start Flash Builder and specify the full path of the public-safety-cop folder as your workspace (the workspace needs to be one folder level above the project folder)

6. Import a Flash Builder project, and choose the __ArcGISViewerForFlex-flexviewer-3.0-src folder as your project folder; cancel the build if one starts automatically

7. Exit Flash Builder and delete the __ArcGISViewerForFlex-flexviewer-3.0-src\bin-debug and __ArcGISViewerForFlex-flexviewer-3.0-src\bin-release folders if present

8. Zip the __ArcGISViewerForFlex-flexviewer-3.0-src folder into __ArcGISViewerForFlex-flexviewer-3.0-src.zip
so that the top-level item in the zip is the __ArcGISViewerForFlex-flexviewer-3.0-src folder

## How To Run Automatic Builds

The Ant program uses the instructions in the file build.xml to unzip a fresh copy of the workspace,
copy the widget and other sources into the workspace, build the widgets, and copy them into the
__distrib distribution directory.

1. At the Windows command line in the public-safety-cop folder, type "ant" to start the Ant build; your compiled widgets will be put into the folder public-safety-cop\__distrib

The script does not delete the __ArcGISViewerForFlex-flexviewer-3.0-src folder that it creates, so
you can use Flash Builder and the public-safety-cop workspace for interactive development and testing.

## How To Set Up for Manual Builds

1. Copy folder "libs"
into the __ArcGISViewerForFlex-flexviewer-3.0-src folder;
confirm folder replace for all items (nothing is actually replaced)

2. Copy the contents of folder "config"
into the __ArcGISViewerForFlex-flexviewer-3.0-src\src folder;
confirm replacement of config.xml

3. Copy the contents of folder "widgetConfigsOnly"
into the __ArcGISViewerForFlex-flexviewer-3.0-src\src\widgets folder;
confirm folder replace for all items (nothing is actually replaced)

4. Copy folders "assets", "com", org", "popups", and "widgets"
into the __ArcGISViewerForFlex-flexviewer-3.0-src\src folder;
confirm folder replace for all items (nothing is actually replaced)

5. Start Flash Builder with the public-safety-cop workspace

6. Right-click on the __ArcGISViewerForFlex-flexviewer-3.0-src project name in the Package Explorer window and select Properties

7. Go to the Flex Modules section

8. Add the module sources BombThreatWidget.mxml, CIWidget.mxml,ClosestFacilityWidget.mxml,
EMHeaderControllerWidget.mxml, EMSplashWidget.mxml, ERGChemicalWidget.mxml,
LivelayerByExceptionWidget.mxml, NationalGridWidget.mxml, PDCWidget.mxml,
ReportByExceptionWidget.mxml, and SwipeWidget.mxml
to the build list for the project

You can now use Flash Builder and the public-safety-cop workspace for interactive development and testing.