---
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

-   __APPS__

    ---

    ![apps_pic](assets/apps.png)

    [:material-cloud-download: APPS](../assets/SAVE-APPLICATION-SYSTEM/APPS.psu)

    - `mc?:/APPS/` used for OpenTuna, Funtuna, Funtuna Fork and possibly more apps. Preferably not used as these all boot `mc?:/BOOT/BOOT.ELF`

-   __BOOT__

    ---

    ![apps_pic](assets/boot.png)

    [:material-cloud-download: BOOT](../assets/SAVE-APPLICATION-SYSTEM/BOOT.psu)

    - `mc?:/BOOT/` Where exploits look to boot from. 

        - `BOOT.ELF` PS2BBL hotkeys and autoboot. Used to standardize both for all exploit types.

        - `BOOT2.ELF` wLE ISR exFAT file browser / ELF launcher (Triangle during PS2BBL logo)

        - `osdmenu.elf` OSDMenu hacked OSDSYS (Autoboot if no key is pressed)

        - `ESR.ELF` ESR for running patched backup (in OSDMenu)

-   __SYS-CONF__

    ---

    ![apps_pic](assets/sys-conf.png)

    [:material-cloud-download: SYS-CONF](../assets/SAVE-APPLICATION-SYSTEM/SYS-CONF.psu)

    - `mc?:SYS-CONF/` Configuration files for the `BOOT` folder and FMCB

</div>

???+ tip "Hotkeys"

    During the PS2BBL logo, you have 4 seconds to activate run these options. On some like R1, it will go down the list till one is found, else exit to OSDSYS.

    ![PS2BBL Hotkeys](./exploits/assets/PS2BBL_Hotkeys.png){ width="800" .on-glb }
    ///caption
    Config @ mc?:/SYS-CONF/PS2BBL.INI and OSDMENU.CNF
    ///

[^1]: Modchips usually require the BOOT folder to be in Memory Card Slot 1 (`mc0:/BOOT/BOOT.ELF`) such as Matrix Infinity, DMS3/4, Ghost 2 and Modbo/Mars Pro