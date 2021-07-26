# Notepad++ integration into GameStudio A8

It supports:
- compiling LiteC and publishing into .exe
- code auto-completion + highlighting for LiteC and HLSL
- sourceCookifier (similar to SEDs code jumper) for LiteC and HLSL
- easy manual search (select world and press CTRL + F1)
- themes, plugins and all other cool notepad++ features

Known issues (solutions can be found below):
- plugin icons on toolbar won't work correctly when Dark Mode is enabled
- sourceCookifier plugin causes a lot of troubles...
- sourceCookifier will throw 'cannot open file' error, if path to the file contains unicode characters
- after 'cannot open file' error if won't update the code jumper, to fix this togggle between session modes
- comment blocks won't hide anything from code jumper (sourceCookifier's parser)
- HLSL has only white theme out of the box (since it's UDL it's not possible to apply themes)
- if your project name has spaces, NppExec might have problems executing it (replace spaces with at least _ )

# How to use
Simply copy Notepad++ folder into your GameStudio rootfolder and it's all set.

To fix void plugin icons after enabling Dark Mode:
- go to: Preferences->General->Toolbar and check 'Standard icons: small' option

If sourceCookifier does something weird with code parsing:
- if it's a .h file make sure to reindent it from notepad++
- run as administrator, to make sure that notepad++ has write/read permissions
- else report it

To get dark theme for HLSL working do:
- close notepad++ if it's opened
- copy 'hlsl_darktheme.xml' into folder called 'userDefineLangs' in Notepad++ rootfolder
- remove 'hlsl.xml' so they won't conflict with eachother
- open notepad++ and enable Dark Mode from Settings->Preferences->Dark Mode
- don't forget to reset icons to 'Standard icons: small' from Settings->Preferences->General
- test .fx file if it's automatically recognized as HLSL file
- if .fx file wasn't recognized, go to Language->HLSL while .fx file was opened

# Shortcuts
- autoindent: CTRL+ALT+A
- open manual: F1
- search manual for selected world: CTRL + F1 (or mouse right and 'help')
- direct execute previous cmd: F5
- open execute... window (to change cmd between publishing and compiling): F6
- go to definition (of a variable, function, etc): CTRL + SHIFT + ENTER

# Screenshots
![Alt text](https://github.com/3RUN/Notepad-plus-plus-for-gamestudio-a8/blob/main/Screenshots/liteC.png?raw=true "LiteC.")
![Alt text](https://github.com/3RUN/Notepad-plus-plus-for-gamestudio-a8/blob/main/Screenshots/hlsl.png?raw=true "HLSL.")

# Sources
Notepad++ (v8.1.2 portable) https://github.com/notepad-plus-plus/notepad-plus-plus

Plugins:
- Custom Toolbar (Author: dw-dev@gmx.com Homepage: https://sourceforge.net/projects/npp-customize)
- LanguageHelp (Author: Franco Stellari Homepage: https://github.com/francostellari/NppPlugins)
- NppExec (Author: Vitaliy Dovgan Homepage: https://github.com/d0vgan/nppexec)
- SourceCookifier (Author: UFO-Pu55y Homepage: https://sourceforge.net/projects/sourcecookifier/)
- TextFX Characters (Author: Chris Severance Homepage: https://sourceforge.net/projects/npp-plugins/files/TextFX/)
- Visual Studio Line Copy (Author: Mackenzie Zastrow (forked by Derek Brown) Homepage: https://sourceforge.net/projects/kered13-notepad-plugins/)
