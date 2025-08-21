---
hide:
  - navigation
  - toc
---

# Universal Memory Card Structure

Abbreviated UMCS, this aims to provide a very robust structure that works for all exploits and hopefully all modchips that support memory card boot via `mc1:/BOOT.BOOT.ELF`

This is the core of SAS (Save Application Strucure) so that there is minimal configuration end users need to do to run memory card based exploits.

Should you ever mess up your config, here are backups to restore. Follow the site [tutorial](../site_tutorial/index.md) to restore these files, otherwise if you do not have entry back in try `R1+Start` to boot `mass:/RESCUE.ELF` Hint: rename [wLE ISR exFAT](https://israpps.github.io/projects/wlaunchelf-isr) to `RESCUE.ELF` and place at root of USB stick.


<div class="grid cards" markdown>

-   __APPS__

    ---

    [:material-cloud-download: APPS](../assets/SAVE-APPLICATION-SYSTEM/APPS.psu)

    ![apps_pic](assets/apps.png)

    - `mc?:/APPS/` used for OpenTuna, Fortuna, Funtuna and possibly more apps.

-   __BOOT__

    ---

    ![apps_pic](assets/boot.png)

    [:material-cloud-download: BOOT](../assets/SAVE-APPLICATION-SYSTEM/BOOT.psu)

    -   `mc?:/BOOT/` Where exploits look to boot from. 

        - `BOOT.ELF` PS2BBL hotkeys and autoboot

        - `BOOT2.ELF` wLE ISR exFAT file browser / ELF launcher

        - `osdmenu.elf` OSDMenu hacked OSDSYS

        - `ESR.ELF` ESR for running patched backup

-   __SYS-CONF__

    ---

    [:material-cloud-download: SYS-CONF](../assets/SAVE-APPLICATION-SYSTEM/SYS-CONF.psu)

    ![apps_pic](assets/sys-conf.png)

    - `mc?:SYS-CONF/` Configuration files for the `BOOT` folder and FMCB

</div>