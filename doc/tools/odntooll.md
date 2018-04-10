OverdriveNTool - tool for AMD Hawaii, Fiji, Polaris, Vega GPUs

Hi all
This application is for editing some parameters in the latest AMD OverdriveNext API supported GPUs (currently 290, 290x, 380, 380x, 390, 390x, Fury, Fury X, Nano, 4xx, 5xx series, Vega 56, Vega 64, Vega FE)
I've made this because WattTool has stopped working since driver 17.7.2.

Requirements:
System: Windows 7 or newer
GPU: AMD 290, 290x, 380, 380x, 390, 390x, Fury, Fury X, Nano, 4xx, 5xx series, Vega 56, Vega 64, Vega FE
Driver: 17.7.2 or newer

Command Line:
-p[gpu_id]"Name"
apply profile "Name" to GPU with id=[gpu_id]
-c[gpu_id]"Name"
same as above, but with confirmation message that application started and everything went ok.
-r[gpu_id]
reset GPU with id=[gpu_id]
cp[gpu_id]"Name"
compare current values of GPU with id=[gpu_id] with profile "Name", and eventually set this profile if not equal
cm[gpu_id]"Name"
compare current values of GPU with id=[gpu_id] with profile "Name", and eventually set this profile if not equal, with additional message if not equal found
co[gpu_id]"Name"
only compare current values of GPU with id=[gpu_id] with profile "Name", with message if not equal found
-consoleonly
displays all messages (eg. errors) in cmd.exe console window, instead of gui messages. Only commands that are put after -consoleonly are affected, example:
"OverdriveNTool.exe" -consoleonly -r0 -p0"1" -r1 -p1"1" -r2 -p2"2" - will affect all commands
"OverdriveNTool.exe" -r0 -p0"1" -r1 -consoleonly -p1"1" -r2 -p2"2" - will affect -p1"1" -r2 -p2"2" commands only

[gpu_id] - it's the first number taken from GPU description, for single video card it's 0
"Name" - name of the profile that was saved ealier, must be quoted if has spaces inside

example:
OverdriveNTool.exe -p0myProfile -p1"Profile 2"
In this example application starts without gui, then sets "myProfile" to GPU with id=0 and "Profile 2" to GPU with id=1 and then exit.

commands can be used all together, for example:
OverdriveNTool.exe -p0myProfile -r0 co1"Profile 1"
On configs with more than 10 GPUs [gpu_id] must have 2 digits, for GPUs 0-9 leading 0 must be added, example: 00,01,02,03,04,05,06,07,08,09,10,11,12. Usage example: -p05"Name"
It's possible to use * as [gpu_id], which means it affects all supported GPUs, example:
-r* -p*MyProfile -p2"Custom profile" cm*MyProfile

Additional info:
-Workaround for bug in 17.7.2 drivers, when driver sometimes uses default voltages instead of user settings: use reset and re-apply profile.
-It's possible to disable/enable each P state. To do this click on P0, P1.. etc. label. If P state is disabled it will not be used by GPU.
-I2C currently supports: IR3567B (RX470, RX480, some RX5xx), up9505 (MSI RX5xx)
-If you prefer to not touch fan settings it's possible to deactivate Fan section for each GPU. To do this press Ctrl + double click somewhere on the Fan box. It's saved per gpu_id, so GUI or commandline will not touch fan settings for such GPU.
-To open Settings or SoftPowerPlayTable editor left click on top-left program icon, or right click on the titlebar.

Current version: 0.2.5 (13.02.2018)
Filename: OverdriveNTool.exe
MD5: 7816F1F8096447F2F8AAF794E0E20B50
SHA-1: 8891359E382256162F9946667E829C429189CB6A

