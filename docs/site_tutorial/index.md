---
hide:
  - navigation
glightbox: true
---

# Tutorial: How to use this sites content

##  What is "SAS"

Otherwise known as `Save Application System`, SAS apps/folders are single directory folders that play nice with the memory card filesystem as subdirectories can easily break it.

__SAS Applications include:__

- [Memory Card icons](icon_meanings) for visual indicator as to apps purpose and critical status to your boot environment. 

- title.cfg for other apps such as OPL,OSD-XMB and PSBBN DEP to list apps to run without user intervention.

- Prefix such as `APP_OPL` (Application)) or `DST_ROMVERCHK` (Diagnostic Service Tool) for ease of navigating in wLE ISR exFAT, and to allow other apps that don't rely on title.cfg to boot such app like OSDMenu allows user to run app from the MC Browser.

- Packaged via a container called a `psu`. This is used to transfer game saves, but adopted for SAS so that all assets are contained. Even date/time is preserved so that Apps are always in order by type alphabetically in the MC Browser!


## Step 1: Open wLaunchELF ISR exFAT

[:material-cloud-download: wLE ISR eXFAT](https://israpps.github.io/projects/wlaunchelf-isr)

![wle_1](assets/wle_1.png){ width="800" data-gallery="tutorial"}

![wle_2](assets/wle_2.png){ width="800" data-gallery="tutorial"}


## Step 2: Navigate to USB and find the APP.psu
![wle_3](assets/wle_3.png){ width="800" data-gallery="tutorial"}

![wle_4](assets/wle_4.png){ width="800" data-gallery="tutorial"}

## Step 3: Installing the APP.psu
![wle_5](assets/wle_5.png){ width="800" data-gallery="tutorial"}

![wle_6](assets/wle_6.png){ width="800" data-gallery="tutorial"}

![wle_7](assets/wle_7.png){ width="800" data-gallery="tutorial"}

![wle_8](assets/wle_8.png){ width="800" data-gallery="tutorial"}

## Step 4: Verifying and understanding wLE icon colors
![wle_9](assets/wle_9.png){ width="800" data-gallery="tutorial"}

![wle_10](assets/wle_10.png){ width="800" data-gallery="tutorial"}

## BONUS: Launching from Browser! (with OSDMenu)
![mcbrowser_1](assets/mcbrowser_1.png){ width="800" data-gallery="tutorial"}

![mcbrowser_2](assets/mcbrowser_2.png){ width="800" data-gallery="tutorial"}




## Badges: visual indicator per/app on website

<div class="grid cards" markdown>

-   ![SASPSU_PIC](../assets/badges/SASPSU.png){ width="75" } ![UMCSPSU_PIC](../assets/badges/UMCSPSU.png){ width="75" }

    ---

    App follows SAS/UMCS guidelines


-   ![SASZIP_PIC](../assets/badges/SASZIP.png){ width="75" } ![UMCSZIP_PIC](../assets/badges/UMCSZIP.png){ width="75" }

    ---

    App follows SAS/UMCS guidelines and must be "Unzipped", then PSU Pasted to root of MemCard

-   ![SAS7z_PIC](../assets/badges/SAS7Z.png){ width="75" } ![SAS7ZIP_PIC](../assets/badges/SAS7ZIP.png){ width="75" } ![UMCS7z_PIC](../assets/badges/UMCS7Z.png){ width="75" } ![UMCS7ZIP_PIC](../assets/badges/UMCS7ZIP.png){ width="75" }

    ---

    App follows SAS/UMCS guidelines and must be "Un7zipped", then PSU Pasted to root of MemCard

-   ![SASRAR_PIC](../assets/badges/SASRAR.png){ width="75" } ![UMCSRAR_PIC](../assets/badges/UMCSRAR.png){ width="75" }

    ---

    App follows SAS guidelines and must be "UnRARed", then PSU Pasted to root of MemCard

-   ![SASEXT_PIC](../assets/badges/SASEXTLINK.png){ width="75" } ![UMCSEXT_PIC](../assets/badges/UMCSEXTLINK.png){ width="75" }

    ---

    App follows SAS/UMCS guidelines and must be downloaded from source, then PSU Pasted to root of MemCard


</div>

  
