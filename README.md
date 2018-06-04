# nord-materia
### This repo serves as an example how to quickly nordify the materia theme.



### Colors which are included in this example:
* nord0
* nord0.5 (50% nord0 50% nord1)
* nord1
* nord5 normal foreground
* nord6 selection foreground and secondary
* nord8 primary color
* nord9 link color
* nord10 selection color and info
* nord11 error and windowclose
* nord13 warning
* nord14 success (or eg. battery in gnome-settings)



#### 1. Create the materia-nord color palette and modify the file to your own needs

~~~
# ~/.colors/materia-nord
BG=353B49
FG=e5e9f0
BTN_BG=3b4252
BTN_FG=e5e9f0
MENU_BG=2e3440
MENU_FG=e5e9f0
ACCENT_BG=88C0D0
SEL_BG=5E81AC
SEL_FG=ECEFF4
TXT_BG=3b4252
TXT_FG=e5e9f0

HDR_BTN_BG=3b4252
HDR_BTN_FG=e5e9f0

WM_BORDER_FOCUS=88C0D0
WM_BORDER_UNFOCUS=2e3440

TERMINAL_COLOR4=81A1C1
TERMINAL_COLOR5=B48EAD
TERMINAL_COLOR9=BF616A
TERMINAL_COLOR10=A3BE8C
TERMINAL_COLOR11=EBCB8B
TERMINAL_COLOR12=5E81AC

GRADIENT=0.0
GNOME_SHELL_PANEL_OPACITY=0.0
MATERIA_STYLE_COMPACT=True
MATERIA_COLOR_VARIANT=dark
UNITY_DEFAULT_LAUNCHER_STYLE=False

NAME=nord
~~~


#### 2. clone the materia theme
~~~
cd ~/.themes
git clone https://github.com/nana-4/materia-theme.git
~~~

#### 3. create a new theme based on the materia-nord color scheme we created
~~~
cd materia-theme
./change_color.sh -o materia-nord ~/.colors/materia-nord
~~~

#### 4. navigate to the new theme in ~/.themes/materia-nord
~~~
cd ../materia-nord
~~~

#### 5. execute custom seds to change some assets. E.g. close buttons:
~~~
sed -i -e 's/#FF5252/#BF616A/' -e 's/#3b4252/#ECEFF4/' -e 's/opacity="0.3"/opacity="0.2"/' gnome-shell/assets/window-close-active.svg
sed -i -e 's/#FF5252/#BF616A/' -e 's/#3b4252/#ECEFF4/' gnome-shell/assets/window-close.svg
~~~
#### your new theme is ready to use :)

### Tipps
* you can change the panel opacity from 0.0 to 1.0 by edititing the GNOME_SHELL_PANEL_OPACITY value
* you can create light themes to but should set MATERIA_COLOR_VARIANT=light
* you can change the size style by setting MATERIA_STYLE_COMPACT=false

not implemented yet: WM_BORDER_*

