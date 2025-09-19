# Quidi-Q2-with-KAMP-fully-integrated
Quidi Q2 Config to enable and integrate KAMP

Guide for Enabling KAMP Features on the Qidi Q2
This guide provides instructions for enabling all features of Klipper Adaptive Meshing and Purging (KAMP) on your Qidi Q2 3D printer. 
KAMP is a native Klipper functionality that enhances the 3D printing process with several key features:
Adaptive Meshing: This feature optimizes the bed leveling process by focusing the mesh generation on the area where the object will be printed, significantly reducing preparation time.
Adaptive Purging: KAMP allows for the creation of a dense purge line near the print area, which minimizes travel movements and ensures a solid purge before printing begins.
Smart Park: The print head can be parked near the print's starting location during the heat-up phase, further minimizing travel distances.
Voron Purge: For users who prefer it, KAMP includes the option to enable a Voron-style purge, which creates a dense purge pattern in the shape of the Voron brand logo.

> [!WARNING]
> The files above were created for my personal use and I cannot be held responsible for what they might do to your printer. Use at your own risk.

# __Procedure for configuring KAMP__
## 1. File management in the Fluidd interface
   
Within the Fluidd web interface, navigate to the Configuration section.

<img width="741" height="698" alt="Untitled" src="https://github.com/user-attachments/assets/26e0af36-3c8c-4b4f-8afa-4e0c75f1db16" />



### There are some file duplication: 

You will notice that the Qidi configuration includes duplicate KAMP files in the main configuration directory. 
For this installation, we will use the files located within the dedicated KAMP folder. <img width="727" height="643" alt="picture 2" src="https://github.com/user-attachments/assets/56ac593b-c509-41c7-81c5-ce23793b568a" />



### Relocate duplicate files: 

To avoid conflicts, create a new folder named "store for delete" or "Backup_KAMP_Files" and move the two duplicate files (KAMP_setting.cfg and Adpative_meshing.cfg) into this new folder. 
This ensures they are not immediately deleted but are properly isolated from the active configuration. 
<img width="971" height="860" alt="picture 3" src="https://github.com/user-attachments/assets/ba843d2a-272b-4304-a3fe-6adc12f4bc27" />



## 2. Update the KAMP_settings.cfg file
Open the KAMP_settings.cfg file, which is located in the KAMP directory.
<img width="957" height="606" alt="picture 4" src="https://github.com/user-attachments/assets/4aa619ea-96dc-46d5-8264-1f04372d3bfe" />


Modify the file path: Change the file path at the top of this file to correctly reference its location within the KAMP folder. This ensures the remaining KAMP configuration files are included properly. 
<img width="1484" height="447" alt="picture 6" src="https://github.com/user-attachments/assets/c65791b4-713a-4274-9938-8565d35d896b" />

## 3. Update the printer.cfg file

Open the printer.cfg file and modify the line that includes the KAMP settings.
Alter the path to point to the KAMP_settings.cfg file located inside the KAMP folder.
<img width="911" height="510" alt="picture 5" src="https://github.com/user-attachments/assets/adcba004-8804-4c5a-bb27-bfcd87bd9ac4" />

## 4. Update the gcode_macro.cfg file
   
Once the KAMP_settings.cfg is included in printer.cfg and the other KAMP files are referenced, the KAMP features are enabled, but they must be called from a macro.

Integrate KAMP into the print_start macro: Open the gcode_macro.cfg file and add the necessary KAMP functions to your Print_start macro. This will instruct the printer to execute the new KAMP features at the beginning of each print. Here all modifications I made to the Print_Start macro

<img width="962" height="810" alt="picture 7" src="https://github.com/user-attachments/assets/42d33fad-c7e5-4bbc-867a-5433211c688c" />

## 5. additionaly change to Start-Gcode in Quidi Studio or Orca slicer  <br>


### first open the Printer Settings 

<img width="962" height="753" alt="picture 8" src="https://github.com/user-attachments/assets/9e381d84-9bf1-4fc4-b21f-7ee172d8f4d2" /> <br>  


### Than modify the Star-Gcode in you printer preset

this will remove the factory purge lines

<img width="1381" height="686" alt="picture 9" src="https://github.com/user-attachments/assets/12da5716-fe11-4195-8121-de714b91f952" /> <br>  


### Don't forget to click save and name your changed version

<img width="1105" height="652" alt="picture 10" src="https://github.com/user-attachments/assets/61bf8469-5857-4d04-89d9-0fd419ec891b" />

