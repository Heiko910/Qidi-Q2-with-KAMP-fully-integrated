# Quidi-Q2-with-KAMP-fully-integrated
Quidi Q2 Config to enable and integrate KAMP

Guide for Enabling KAMP Features on the Qidi Q2
This guide provides instructions for enabling all features of Klipper Adaptive Meshing and Purging (KAMP) on your Qidi Q2 3D printer. 
KAMP is a native Klipper functionality that enhances the 3D printing process with several key features:
Adaptive Meshing: This feature optimizes the bed leveling process by focusing the mesh generation on the area where the object will be printed, significantly reducing preparation time.
Adaptive Purging: KAMP allows for the creation of a dense purge line near the print area, which minimizes travel movements and ensures a solid purge before printing begins.
Smart Park: The print head can be parked near the print's starting location during the heat-up phase, further minimizing travel distances.
Voron Purge: For users who prefer it, KAMP includes the option to enable a Voron-style purge, which creates a dense purge pattern in the shape of the Voron brand logo.

Procedure for configuring KAMP
1. File management in the Fluidd interface
   
Within the Fluidd web interface, navigate to the Configuration section. See picture 1<img width="741" height="698" alt="Untitled" src="https://github.com/user-attachments/assets/26e0af36-3c8c-4b4f-8afa-4e0c75f1db16" />

Acknowledge file duplication: You will notice that the Qidi configuration includes duplicate KAMP files in the main configuration directory. For this installation, we will use the files located within the dedicated KAMP folder. See Picture 2
Relocate duplicate files: To avoid conflicts, create a new folder named store for delete or Backup_KAMP_Files and move the two duplicate files (KAMP_setting.cfg and Adpative_meshing.cfg) into this new folder. This ensures they are not immediately deleted but are properly isolated from the active configuration. See picture 3
2. Update the printer.cfg file
Open the printer.cfg file and modify the line that includes the KAMP settings. See Picture 5
Change the path: Alter the path to point to the KAMP_settings.cfg file located inside the KAMP folder.
3. Update the KAMP_settings.cfg file
Open the KAMP_settings.cfg file, which is located in the KAMP directory. See picture 4 
Modify the file path: Change the file path at the top of this file to correctly reference its location within the KAMP folder. This ensures the remaining KAMP configuration files are included properly. See picture 6
4. Update the gcode_macro.cfg file
Once the KAMP_settings.cfg is included in printer.cfg and the other KAMP files are referenced, the KAMP features are enabled, but they must be called from a macro.
Integrate KAMP into the print_start macro: Open the gcode_macro.cfg file and add the necessary KAMP functions to your Print_start macro. This will instruct the printer to execute the new KAMP features at the beginning of each print. See picture 7 for all modifications I made to the Print_Start macro
