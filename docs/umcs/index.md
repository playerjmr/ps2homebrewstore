---
icon: simple/builtbybit
hide:
  - navigation
  - toc
---

# Universal Memory Card Structure

Abbreviated UMCS, this aims to provide a very robust structure that works for all exploits and hopefully all modchips that support memory card boot via `mc?:/BOOT/BOOT.ELF`[^1]


This is the core of SAS (Save Application Strucure) so that there is minimal configuration end users need to do to run memory card based exploits.

Should you ever mess up your config, here are backups to restore. Follow the site [tutorial](../site_tutorial/index.md) to restore these files, otherwise if your PS2 still shows the PS2BBL boot logo, try `R1+Start` to boot `mass:/RESCUE.ELF`

!!! tip "RESCUE.ELF"

    Download and Rename [wLE ISR exFAT](https://israpps.github.io/projects/wlaunchelf-isr) to `RESCUE.ELF` and place at root of USB stick.

<div class="grid cards" markdown>

-   __APPS__![umcs-psu_pic](../assets/badges/UMCSPSU.png){ width="75" }

    ---

    ![apps_pic](assets/apps.png)

    [:material-cloud-download: APPS](../assets/SAVE-APPLICATION-SYSTEM/APPS.psu)

    - `mc?:/APPS/`  
        Used by OpenTuna, Funtuna, Funtuna Fork and possibly more apps as hotkeys. Hoping to code out OpenTunas hotkeys and bad hardpaths.
    

    - A great place to put apps that do not have icons and define in your hacked OSDSYS config file!

-   __BOOT__![umcs-psu_pic](../assets/badges/UMCSPSU.png){ width="75" }

    ---

    ![apps_pic](assets/boot.png)

    [:material-cloud-download: BOOT](../assets/SAVE-APPLICATION-SYSTEM/BOOT.psu), [:material-cloud-download: BOOT MMCE](../assets/SAVE-APPLICATION-SYSTEM/BOOT-MMCE.psu) or [:material-cloud-download: BOOT MX4SIO](../assets/SAVE-APPLICATION-SYSTEM/BOOT-MMCE.psu)

    - `mc?:/BOOT/`  
        Where exploits look to boot from. 


    - `mc:/BOOT/BOOT.ELF`  
        PS2BBL hotkeys and autoboot. Used to standardize both for all exploit types. May have additional MMCE or MX4SIO drivers.


    - `mc:/BOOT/BOOT2.ELF`  
        wLE ISR exFAT file browser / ELF launcher (Triangle during PS2BBL logo)


    - `mc:/BOOT/ESR.ELF`  
        ESR for running patched backup (in OSDMenu)

    !!! info "Pair the BOOT folder with your exploit"

        For consistency, use the correct BOOT, BOOT MMCE or BOOT MX4SIO download for the device you are using, same for the exploit you are using. MMCE downloads have MMCE drivers already. For [exploits that need installs](../exploits/), use the same device driver installer.

-   __SYS-CONF__![umcs-psu_pic](../assets/badges/UMCSPSU.png){ width="75" }

    ---

    ![apps_pic](assets/sys-conf.png)

    [:material-cloud-download: SYS-CONF](../assets/SAVE-APPLICATION-SYSTEM/SYS-CONF.psu)

    - `mc?:/SYS-CONF/`  
        Configuration files for the `BOOT` folder other apps that look here.


    - `mc:/SYS-CONF/PS2BBL.INI / PSXBBL.INI`  
        PS2BBL's config file. Supports 9 paths.


    - `mc:/SYS-CONF/LAUNCHELF.CNF`  
        wLE ISRs config file


    - `mc:/SYS-CONF/OSDMENU.CNF`  
        OSDMenu's config file


    - `mc:/SYS-CONF/FREEMCB.CNF`  
        FreeMCBoot's config file


    - `mc:/SYS-CONF/IPCONFIG.DAT`  
        Network config shared between many homebrew apps.

</div>

## When is PS2BBL's config called?

```mermaid
---
config:
  theme: mc
  layout: elk.forced
  look: classic
---
graph LR
    A(["PS2 Power On/Reset"]) L_A_B_0@-- "BOOTROM 1.00-2.20" --> B["OSDSYS UPDATE<br>B?EXEC-SYSTEM<br>(PS2BBL/ProtoPwn)<br>./CONFIG.INI <br>DOES NOT EXIST!"]
    A L_A_n1_0@-- "BOOTROM 2.30,2.50<br>and DEV 1 Modchips" --> n1["OPENTUNA/DEV 1 CHIPS<br>mc?:/BOOT/BOOT.ELF<br>(PS2BBL)<br>./CONFIG.INI <br>DOES NOT EXIST!"]
    B L_B_n5_0@-- "Fall back to SYS-CONF" --> n5@{ label: "<pre style=\"font-family:\"><code style=\"font-family:\">mc?:/SYS-CONF/PS2BBL.INI</code></pre>" }
    n1 L_n1_n5_0@-- "Fall back to SYS-CONF" --> n5
    n5 --> n6["AutoLaunch<br>or<br>Hotkeys"]
    n6 --> n7@{ label: "<span style=\"color:\">PS2BBL.INI AUTOLAUNCH</span><br style=\"color:\"><br style=\"color:\"><span style=\"color:\">1: SYS_OSDMENU</span><br style=\"color:\"><br style=\"color:\"><span style=\"color:\">2: SYS_FMCBD-1966</span><br style=\"color:\"><br style=\"color:\"><span style=\"color:\">3: SYS_FMCBD-1965</span><br style=\"color:\"><br style=\"color:\"><span style=\"color:\">4: SYS_FMCBD-1955</span><br style=\"color:\"><br style=\"color:\"><span style=\"color:\">5: BOOT/BOOT2.ELF</span>" }
    B@{ shape: rect}
    n1@{ shape: rect}
    n5@{ shape: proc}
    n6@{ shape: diam}
    n7@{ shape: lin-proc}
     A:::Ash
    classDef Ash stroke-width:1px, stroke-dasharray:none, stroke:#999999, fill:#EEEEEE, color:#000000
    style A stroke:#00C853,fill:#00C853,color:none
    style B color:#D50000,fill:transparent
    style n1 color:#D50000,fill:transparent
    style n5 fill:transparent,color:#00C853
    style n6 fill:#00C853
    style n7 fill:#FFF9C4
    linkStyle 0 stroke:#00C853,fill:none
    linkStyle 1 stroke:#00C853,fill:none
    L_A_B_0@{ animation: slow } 
    L_A_n1_0@{ animation: slow } 
    L_B_n5_0@{ animation: slow } 
    L_n1_n5_0@{ animation: slow }

```

!!! info "Landing on your hacked OSDSYS of choice:"

    PS2BBL.INI and PSXBBL.INI have already been setup so that minimal config changes are needed if at all. To land on your hacked OSDSYS of choice, install the OSDMenu/ FMCB Version XXXX as needed. If multiple are installed (such as the MMCE AIO downloads), you can delete in order from first to last to land on the desired app. This is especially useful for modchip users as they may not play well or at all with some or all of the OSDSYS such as I believe Mars Pro. In that case, just delete all of the SYS_OSDMENU and SYS_FMCB-XXXX folders. Modchip users may need to disable chip to do so.


!!! tip "Hotkeys"

    During the PS2BBL logo, you have 4 seconds to activate run these options. On some like R1, it will go down the list till one is found, else exit to OSDSYS.

    ![PS2BBL Hotkeys](../exploits/assets/PS2BBL_Hotkeys.png){ width="800" .on-glb }
    ///caption
    Config @ mc?:/SYS-CONF/PS2BBL.INI and OSDMENU.CNF
    ///






[^1]: Modchips usually require the BOOT folder to be in Memory Card Slot 1 (`mc0:/BOOT/BOOT.ELF`) such as Matrix Infinity, DMS3/4, Ghost 2 and Modbo/Mars Pro