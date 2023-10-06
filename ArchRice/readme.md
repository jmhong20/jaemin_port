1. Create user
- `useradd -mg wheel *name*`
2. Set password for new user
- `passwd *name*`
3. Modify user pseudo access
- `vim /etc/sudoers`
- Image
- ![웹 캡처_5-10-2023_20956_www youtube com](https://github.com/jmhong20/jaemin_port/assets/59593685/aac106e5-0ea3-4da1-9e08-9d4a890efea4)

==================================================================================================================
## Install: dwm, st, dmenu
1. Install git
- `sudo pacman -S git`
2. Make directory for all source codes
- `mkdir -p .local/src`
- `cd .local/src/`
3. Install dwm
- `git clone https://github.com/bugswriter/dwm.git`
4. Install dmenu
- `git clone https://github.com/bugswriter/dmenu.git`
5. Install st
- `git clone https://github.com/bugswriter/st.git`
6. Make clean install: dwm
- `cd dwm/`
- `sudo pacman -S libxft`
- `sudo pacman -S libxinerama`
- `sudo make clean install`
7. Make clean install: st
- `cd ../`
- `cd st/`
- `sudo make clean install`
8. Make clean install: dmenu
- `cd ../`
- `cd dmenu/`
- `sudo make clean install`
9. Config xinit
- `cd`
- `cp /etc/X11/xinit/xinitrc ~/.xinitrc`
- `vim .xinitrc`
- Image
- ![웹 캡처_6-10-2023_94739_www youtube com](https://github.com/jmhong20/jaemin_port/assets/59593685/6feaffbd-6b8c-47aa-af3a-cb2c8faac15e)
10. Install fonts
- `sudo pacman -S ttf-jetbrains-mono ttf-font-awesome`
11. Start into dwm
- `startx`
- keybindings: Image
- ![웹 캡처_6-10-2023_94936_www youtube com](https://github.com/jmhong20/jaemin_port/assets/59593685/b6d8e697-b802-4522-9496-9078d7bf5641)
