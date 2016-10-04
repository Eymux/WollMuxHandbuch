Linux
-----

### Manual Installation under Linux

#### Installing the OpenOffice.org Extension

-   [Download the file containing WollMux.oxt](Download_WollMux.md "wikilink") of the desired version to a directory &lt;DIR&gt; of your choice.

-   Close all open OOo windows, as well as the
    [WollMuxBar](WollMuxBar "wikilink").

> **WARNING** Please make sure no “soffice” processes are still running.

</div>
-   Open a root shell (console command `sudo -s -H`)
-   Set the correct *umask*, so that normal users don't lose read and
    execute rights:

`umask 022`

-   Uninstall any old OOo extension with following command:

`unopkg remove WollMux.oxt --shared`

-   To install the new OOo extension:

`unopkg add --shared <DIR>/WollMux.oxt`

For a user-level installation the option "--shared" can be omitted,
although this is not recommended. Running WollMux installations
system-wide and WollMux installations at the user level concurrently can
cause problems. WollMux does not support this, therefore.

#### Installing the WollMuxBar

-   [Download the file *WollMuxBar.jar*](Download_WollMux.md "wikilink");
    save in directory */usr/share/java*
-   [Download the file *wollmuxbar*](Download_WollMux.md "wikilink"); save
    in directory */usr/bin*

The WollMuxBar can then be started with the console command *wollmuxbar*
or (using the complete path) */usr/bin/wollmuxbar*. You can create a
corresponding shortcut on the desktop.


> **INFO** If you use [LibreOffice](http://www.libreoffice.org), please see **[Tips for starting the WollMuxBar with LibreOffice](WollMuxBar.md#libreoffice "wikilink")**.

Windows
-------

### EXE Installer for Windows

There is an EXE installer for Windows
(*wollmux-<VERSION>-installer.exe*) available. It will install
[WollMux](WollMux.md "wikilink") as well as the
[WollMuxBar](WollMuxBar.md "wikilink") on your system, and (optionally)
shortcuts on the desktop und in the Start menu.

**Tips:**

-   To successfully run the EXE installer you need
    Administrator privileges.
-   The EXE installer attempts to close any OpenOffice windows that may
    be open before installation.
-   Installation with the EXE installer always takes place
    system-wide, i.e. desktop and Start menu shortcuts, as well as
    uninstaller entries, are installed for all users. The OpenOffice.org
    extension is installed as if the console command *unopkg add
    --shared* had been given.
-   OpenOffice.org and Java must be installed on your system
    before installation.

#### Unattended Installation

The EXE installer allows *unattended installation*, that is, during
installation no user interaction is required and no GUI is displayed. To
run the EXE installer in this mode, add the option **--SILENT** oder
**/S** after the executable file name (The uninstaller
`wollmux_unistall.exe` only recognizes the **/S** option):

`wollmux-<VERSION>-installer.exe --SILENT`

> **INFO** If you run the installer with the '--SILENT'' or */S* option,
you will receive no message as to whether the installation was
successful or not.

The EXE installer installs WollMux + WollMuxBar as a default in the
directory *C:\\Program Files\\wollmux* and places shortcuts in the Start
menu and on the desktop. If you want to change this behavior for an
unattended installation, you have the following command line options
available (case-insensitive and order-insensitive):

- **--INSTDIR="&lt;Installation_Path&gt;"** : Determines the installation directory for WollMux.
- **--NOSTARTMENU** : Indicates that the installer should not create Start menu shortcuts.
- **--NODESKTOP** : Indicates that the installer should not create desktop shortcuts.
- **--LOCAL** : Indicates that installer should perform a user-level installation, and not a system-wide installation for all users.

  > **WARNING** In general, this option is NOT advisable! The uninstaller generated by the EXE installer does not support this option. This means uninstalling Wollmux using the uninstaller won't work. In addition, mixing user-level and system-level installations can lead to problems and is not supported by Wollmux. If you do choose this option, however, you can run the installer without Administrator privileges.\

- **--NOKILL** : This command line option, which also works with the uninstaller, prevents any attempt to stop existing “soffice” processes while installing or uninstalling. Without this option, the installer attempts to end “soffice” processes cleanly, using a Java tool; in certain scenarios this can, however,lead to problems (for example, when the [WollMuxBar](WollMuxBar "wikilink") is started with the Quickstarter option), preventing the installer from performing a clean installation. If this happens, please use the NOKILL option, making certain before running the installer that no “soffice” processes are running any longer.

  > **WANRING** If you're going to use the installer with LibreOffice, use of the NOKILL option is mandatory!

- **--LIBRE** : If this option is given, the installer first tries to find an OpenOffice.org installation. Only if no OpenOffice.org installation is found will it look for a LibreOffice installation to use. If you want to bypass installation for OpenOffice.org and install for LibreOffice exclusively, use the --LIBRE option.

  > **WARNING** If you're going to use the EXE installer with LibreOffice, setting the NOKILL option is mandatory! See also [Tips for starting the WollMuxBar with LibreOffice](WollMuxBar#LibreOffice "wikilink").

**Example:**

You want to perform an unattended installation in the directory
*E:\\Example\\WollMux*. There should be no Start menu entry (but you do
want a link on the desktop):

`wollmux-<VERSION>-installer.exe --SILENT --INSTDIR="E:\Example\WollMux" --NOSTARTMENU`

### Manual Installation under Windows

#### Installing the OpenOffice.org extension

The UNO package WollMux.oxt can be installed for a single user or
system-wide for all users. For a **Single-user installation** the
following steps are required:

-   Prerequisite: OpenOffice.org has been completely installed, and
    started at least once, so that user-specific initial setup has
    already been performed.
-   [Download the WollMux.oxt package](Download_WollMux.md "wikilink") of
    the desired version to a directory &lt;DIR&gt; of your choice.

-   Close all open OOo windows, the Quickstarter in the taskbar next to
    the clock, and the [WollMuxBar](WollMuxBar "wikilink").

    > **WARNING** Using Task Manager, please make sure no “soffice” processes
are still running. If they are, use Task Manager to stop them.

-   Install the UNO package with the following command, using values
    suitable for your environment:
    -   &lt;OOo_Path&gt;: The full path to the directory where OpenOffice.org
        is installed.

        **Ex.** “C:\\Program Files\\OpenOffice.org 3”.
    -   &lt;DIR&gt;: Location (full path) of the downloaded Wollmux package.

`"`<OOo_Path>`\program\unopkg" add "`

<DIR>
\\WollMux.oxt"

For **System-wide installation** add the command line option "--shared".
The appropriate command, requiring Administrator privileges, looks like
this:

`"<OOo_Path>\program\unopkg" add "<DIR>\\WollMux.oxt" --shared`

If you want to uninstall WollMux.oxt system-wide, run the following
command, again requiring Administrator privileges:

`"<OOo_Path>\program\unopkg" remove WollMux.oxt --shared`

#### Installing the WollMuxBar

-   Create the directory where you want the WollMuxBar to be installed,
    for example *C:\\Program Files\\wollmux*
-   [Download](Download_WollMux.md "wikilink") the files *WollMuxBar.jar*
    and *wollmuxbar.exe* and copy them into the directory you
    just created.

Start the WollMuxBar by simply double-clicking *wollmuxbar.exe* (a Java
JRE installation is required). You can create shortcuts to
*wollmuxbar.exe* on the desktop or the Start menu if you like.

#### Install using LibreOffice Portable

See [WollMux with LibreOffice Portable](WollMux_mit_LibreOffice_Portable.md "wikilink")

> **INFO** If you use [LibreOffice](http://www.libreoffice.org), please see **[Tips for starting the WollMuxBar with LibreOffice](WollMuxBar#LibreOffice "wikilink")**.

<Category:Eierlegender_WollMux> <Category:Handbuch_des_WollMux>