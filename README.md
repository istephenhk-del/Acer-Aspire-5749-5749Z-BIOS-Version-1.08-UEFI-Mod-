# Acer-Aspire-5749-5749Z-BIOS-Version-1.08-UEFI-Mod-
A bios for 5749/5749Z with PARTIAL UEFI support (no secure boot)
This bios is based on 5749z bios 1.08, EFI modules are added (Emuvariable, DiskIO, FAT, Partition, LaunchApp) from other BIOSes, e.g. Acer Aspire V5-131 bios version 2.21 and Acer Timeline 3810T bios1.15 
Early Insyde EFI BIOSes have a hybrid architecture, Acer stripped out some modules that are required for UEFI mode to work:
DiskIO DXE Driver
FAT DXE Driver
Partition DXE Driver
Emuvariable DXE Driver
LaunchApp DXE Driver
DiskIO, Partition are from V5-131, the rest are from Timeline  
These DXE drivers are injected into the DXE volume via UEFITool (old engine) 
link:https://github.com/longsoft/uefitool
After injecting the EFI modules,the PE32 of the SetupUtility DXE Driver is extracted as an ffs file.
Use Universal IFR Extractor to extract the ffs into a txt file (link:https://github.com/LongSoft/Universal-IFR-Extractor/releases/tag/v0.3.6)
Use HxD to modify the ffs to unhide menus
Replace the PE32 section with modified one
Save the image
Use Acer Crisis Mode to flash the bios:
Hold Fn+Esc on startup until the fans start to spin loudest
Wait patiently for the flash to complete
Your laptop will reboot after flash completion
