#  smlinux -Super Mario Linux- Install Build Update Script
[<strong>Click here to jump to Frequently Asked Questions</strong>](#frequently-asked-questions)  
<img src=https://github.com/enigma9o7/smlinux/raw/screenshot/MarioPC-small.png> 
## **What does smlinux do?**
#
1. Installs Required Packages (build tools & other dependencies)
2. Installs latest version of itself to path 
3. Clones (downloads) sm64 source repository from Github
4. Extract assets from ROM and prepares for use
5. Optionally applies community sourced upscale modifications 
6. Makes (compiles and links) into binary
7. Creates Menu Entry & Desktop Shortcut
8. Launches Super Mario 64 on your Personal Computer or Android Device!

...and! you can use it again later to quickly rebuild and sync to the latest updates from github.
<img src=https://github.com/enigma9o7/smlinux/raw/screenshot/screenshot1.png> 
## **Download & Installation Instructions**    

Paste either of the following into a terminal then press Enter/Return (*whichever works for your OS*):  
  
`bash -c "$(curl -fsSL https://raw.githubusercontent.com/enigma9o7/smlinux/master/smlinux)"`  
 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; **-OR-**  
`wget https://raw.githubusercontent.com/enigma9o7/smlinux/master/smlinux;bash smlinux;rm smlinux`
	
**That's all you have to do** for ubuntu, debian, arch, macOS, or msys2! You may be prompted to:  
(1) provide password to install build tools (2) approve or change build options (3) specify your romfile .  
smlinux will then run unattended and before the time you finish reading the FAQ you will hear "It's me, Mario!".  
You must provide your own legally backed up Super Mario 64 ROM file.  
*Do not run smlinux as root; you will be prompted for sudo password if needed.* 

[<strong>Click here for Linux distributions that are not debian or arch based.</strong>](#what-dependencies-are-needed-or-installed)  
## **How do I run smlinux again?**
	smlinux
	
smlinux puts a copy of itself into a bin folder in your path, which you can locate with `which smlinux`.  After initial installation, just enter`smlinux`into a new terminal and you will be presented with a menu (as shown in above screenshot) or use command line options (as shown in following screenshot) to the skip menu.  

<img src=https://github.com/enigma9o7/smlinux/raw/screenshot/screenshot1.jpg>

If your pc of terminal freeze during build, set `MAXJOBS=1`. When undefined, smlinux will allow make to run multiple jobs which speeds up compilation on PCs with multiple cores and plenty of memory, but occasionally causes issues on under-powered systems (that can still run the game just fine).

**_macOS notes_**
sm64ex,r96ex,sm64ex-coop and cheaterex all confirmed working with Intel based macOS 10.12 Sierra and newer.  sm64nx and android builds are not working yet.  DOS builds will not be supported.  If you do not already have homebrew and/or Apple X-code command line tools installed, smlinux will install homebrew and homebrew will install the xcode tools, but you may have to enter your password twice and it can take quite a while.  You may also be prompted to grant terminal permission to your Desktop or Applications folder for shortcut installation.  

**Windows notes**
For Android & DOS builds use WSL.  For native builds under Microsoft Windows, first install msys2 and run smlinux from the included mingw terminal. sm64nx builds are not working yet.  Because whiptail is not available for msys, smlinux will run in with no menus or prompts and config file will open automatically. 

**32-bit notes** 
sm64nx and Discord Rich Presence are not suppored.

# Frequently Asked Questions
* [<strong>What does smlinux do?</strong>](#what-does-smlinux-do)
* [<strong>How do I download and install smlinux?</strong>](#download--installation-instructions)      
* [<strong>How do I run smlinux again? Where did it install itself to?</strong>](#how-do-i-run-smlinux-again)
* [<strong>What preset/repo/branch should I chose?</strong>](#what-presetrepositorybranch-should-i-use)
* [<strong>What does the InstallHD option do?</strong>](#what-does-the-install-option-do)
* [<strong>What does the InstallSGI option do?</strong>](#what-does-the-installsgi-option-do)
* [<strong>What does the FPS60 option do?</strong>](#what-does-the-fps60-option-do)
* [<strong>What about other branches?</strong>](#what-about-other-branches)
* [<strong>When to use RENDER_API=GL_LEGACY?</strong>](#when-to-use-render_apigl_legacy)
* [<strong>How to update, rebuild, or change build options later?</strong>](#how-to-update-rebuild-or-change-build-options-later)
* [<strong>How do I build a different version?</strong>](#how-do-i-build-a-different-version)
* [<strong>How to I configure options like controllers, camera, rumble, etc?</strong>](#how-to-i-configure-options-like-controllers-camera-rumble-etc)
* [<strong>Where are my configuration files and saved games stored?</strong>](#where-are-my-configuration-files-and-saved-games-stored)
* [<strong>Are there any cheats?</strong>](#are-there-any-cheats)
* [<strong>How do I apply external data such as textures?</strong>](#how-do-i-apply-external-data-such-as-textures)
* [<strong>How to apply a patch?</strong>](#how-to-apply-a-patch)
* [<strong>How to remove a patch?</strong>](#how-to-remove-a-patch)
* [<strong>What depenencies are needed or installed?</strong>](#what-dependencies-are-needed-or-installed)
* [<strong>How do I create my rom file?</strong>](#how-do-i-create-my-rom-file)
* [<strong>How do I remove everything smlinux created during install?</strong>](#how-do-i-remove-everything-smlinux-created-during-install)
* [<strong>How do I tell smlinux to download sm64 repositories to a folder other than home?</strong>](#how-do-i-tell-smlinux-to-download-sm64-repositories-to-a-folder-other-than-home)
<img src=https://github.com/enigma9o7/smlinux/raw/screenshot/presets.png>

## **What preset/repository/branch should I use?**
If you want to build for PC, the source repository from the team who decompiled the rom, sm64-port, offers the cleanest code and duplication of N64, with currently very few add-ons available.  The unofficial forks, sm64ex and sm64nx, include enhancements and support for many add-ons (which are optional on sm64ex).  sm64ex offers the most flexibility, but you are encouraged to build more than one and try for yourself.  Further forks of sm64ex offer additional enhancements, such as render96ex with additional language support and game features, sm64ex-coop for a 2 player network mode, or cheaterex for all the latest experimental add-ons. For android or web, presets are available based on sm64-port or sm64ex, while for for dos sm64-port based forks are used. 

## **What does the InstallHD option do?**

This will apply HD Mario (Old School V2) and HD Bowser character models and the 3D Coin Patch to most forks except dos.  Render96ex instead gets the Render 96 SGI Model pack which includes Mario, Bowser, 3D coins, and much more.

On sm64pc/sm64ex based forks upscaled textures will aslo be added to your build from the Cleaner Aesthetics github repo, and high quality sounds from MapAnon's github release.  On the render96ex fork, Render96's HD rextures will be used instead, which are over 500MB so require additional download time, as well as more than 2GB of free memory and additional time to precache before game launches.  

On the sm64nx fork, Arredondo's HD Mario & Bowser and Cleaner Aesthetics textures are set as defaults, along with a few other small add-on paks which can be enabled from the in-game mod selection menu, including an HD Luigi model replacement.

*Some of these addons require files remaining available in discord or github, so not gauranteed to work.  What is included with this option may periodically change as new mods are released.*

## **What does the InstallSGI option do?**

For the render96ex preset, this will apply Render96's SGI model pack version 1.42.  On sm64ex-coop a co-op specific version that includes Luigi is applied, while for sm64ex based forks, version 1.3 is applied.    For r96alpha and r96proto presets, the latest 2.0 modelpack is applied.

For sm64nx, this option will add paks for Render96's SGI Models (version 1.3) and Render96's HD textures and set them as defaults.  Be aware this model pak for sm64nx has minor visual problems and is no longer mainained, but can easily be reverted to default or HD models with the in-game mod menu that *only* sm64nx offers.

## **What does the FPS60 option do?**

On repositories that provide a 60fps patch (currently sm64-port, render96ex, and sm64ex-nightly) it will be applied when this option set to 1, and reverse applied when set to 0.  Note that some forks (such as sm64ex-coop, cheaterex, and sm64nx) are already 60fps without a patch and this setting will have no effect.  The currently available patch for sm64ex uses interpolation and may require adjustments to in-game vsync setting for smooth performance, and may not work correctly on displays that aren't 60/120Hz and may not perform well on older computers.

## **What about other branches?**

If you chose one of the presets from the smlinux preset table above, the appropriate branch is used automatically.  For example with `PRESET=sm6ex` the nightly branch is used; if you would like the master branch instead use `PRESET=sm64pc`. If sm64ex nightly works for you, it is reccommend it as it has the latest features and fixes, but if a recent change causes build failure or other problems, use the more stable sm64pc master. For advanced users, branches other than those defined by preset can be built by setting `PRESET` to any undefined name, in which case smlinux will use the the user specified `GIT` and `BRANCH`settings.

## **When to use RENDER_API=GL_LEGACY?** 
*only applies to sm64pc/sm64ex based forks*

For old video cards that support OpenGL 1.1 but not 2.1 (from year 200X).  Check your OpenGL version with the following command: 
	
	glxinfo | grep "OpenGL version"
 
If 1.1-2.0, you must use the legacy renderer.  For 2.1 or greater, standard GL renderer is reccommended, although some old computers that do support 2.1 may perform better with the legacy renderer.

## **How to update, rebuild, or change build options later?**
    
	smlinux update <options>
For example: 
 
	smlinux update
	       or
	smlinux update --hd
	       or
	smlinux update --config
		or
	smlinux update --sgi

Updates existing install to latest from github while retaining custom textures and addons.  If updated source fails to build, restores previous build.

You can also use this option to rebuild after you apply patches or edit your source or source assets like actors manually.

Note` --config` is only needed if `CONFIG=0` in your config file, otherwise it will come up automatically.

Note` --hd` or `--sgi` only do anything if `InstallHD=0` or `InstallSGI=0` in smlinux configuration.  After these add-ons are installed, setting configuration value to 0 will not remove them, only prevent smlinux from reapplying them.

Note smlinux automatically saves one previous build by adding the suffix .old to its foldername (and restores it if your update fails to build). If you want prevent it from being erased during the next update, rename it (anything) before running smlinux, for example: 
 
	mv ~/sm64pc/build/us_pc.old ~/sm64pc/build/firstbuild

## **How do I build a different version?**

	smlinux build --config

Change your preset to another version and it will be installed in its own folder with its own seperate menu entry.  You can build as many versions as you like.  If you wish to build a version other than a predefined preset, leave preset blank or make your own name (which will be used for its foldername), and set GIT and BRANCH.

Note `--config` is only necessary if `CONFIG=0`and/or you havent edited your smlinuxcfg.txt before build.


## **How to I configure options like controllers, camera, rumble, etc?**
*does not apply to sm64-port repository*

Pause then press R with controller or R_Shift with keyboard. For the controller settings, it is recommended to keep the first column for keyboard controls and using the middle for controller. Use the third column if you want additional keys/buttons assigned to the same function, or for mouse buttons. Be sure to map something to L for use with the camera or cheats. I personally enable mouse control for camera increase center aggression significantly. 

You can also just edit the configuration file with any text editor.

## **Where are my configuration files and saved games stored?**

~/.local/share/smlinux smlinux  
~/.local/share/sm64pc sm64pc/ex master  
~/.local/share/sm64ex sm64pc/ex nightly 
~/.local/share/sm64ex-coop sm64ex-coop   
~/.local/share/render96ex render96ex *only if launched with shortcut*  
~/.local/share/cheaterex cheaterex *only if launched with shortcut*    
~/.local/share/sm64-port sm64-port *only if launched with shortcut*    
~/.local/share/sm64nx sm64nx *smlinux creates links in game dir*  

## **Are there any cheats?**

On all forks besides sm64-port, some cheats are built in and enabled automatically if launched from shortcut, and can be found in-game in options menu accessible  when paused.  On compatible sm64ex based forks additional cheats are applied with $4Y$'s CHEATER patch and PeachyPeaches' Dynamic Option System.

## **How do I apply external data such as textures?**

Texture and sound packs can be added to the appropriate resource folder after build.

sm64pc/sm64ex based versions:  
Put the zipfile (or gfx or sound folder) directly into build/us_pc/res and the next time you run the game it'll use it automatically.  The zip file must contain a "gfx" and/or "sound" folder. Do not move or remove base.zip, it should remain in "res" as fallback.
  
sm64nx:  
Create a subdirectory in build/us_pc/romfs for each pak and place the pak file inside, and the next time you run the game it'll load that pak automatically. If you would prefer it to start disabled, use ~ at the beginning of the folder name.  Do not move or remove !!base.pak, it should remain in "romfs" as fallback.

## **How do I apply a patch?**
*change path from sm64pc to sm64-port/sm64ex/etc as appaproriate*

Put the patch file into ~/sm64pc/enhancements (or specify the path differently when applying):
   
	cd ~/sm64pc
	git apply enhancements/filename.patch
	smlinux update
	
If the patch errors when you try to apply it, and you want to use it anyway, you can force it to apply with:
	
	git apply --reject enhancements/filename.patch

## **How do I reverse (remove) a patch?** 
*change path from sm64pc to sm64-port or sm64ex for newer repos*
   
	cd ~/sm64pc
	git apply -R enhancements/filename.patch
	smlinux update

## **How do I apply a patch after 60fps but before Dynamic Options or CHEATER?**  

The following are examples for advanced users to use as reference:

Starting from scratch:

1. Prepare clean source: `smlinux clone`  
2. Change to folder you just prepared: `cd ~/sm64ex`  
3. Apply 60fps: `git apply enhancements/60fps*.patch`  
4. Apply custom patch: `git apply enhancements/custom.patch`  
5. Build with 60fps disabled in smlinux configuration: `smlinux update`  

If you enable 60fps in smlinux configuration, smlinux will attempt to apply as it does not know you have already applied it.  

Starting from previous build with 60fps already applied - and maybe cheater or and dynos too:  

1. Reverse apply CHEATER: `git apply -R enhancements/CHEATER*.patch`  
2. Remove CHEATER patchfile: `rm enhancements/CHEATER.patch`  
3. Reverse apply DynOS `git apply -R enhancements/DynOS*.patch`  
4. Remove DynOS patchfile: `rm enhancements/DynOS*.patch`  
5. Apply your custom patch: `git apply enhancements/custom.patch`  
6. Build with same settings: `smlinux update`  

This works because when smlinux applied the 60fps patch it touched a file called 60fps.  It will apply cheater or dynos if they are enabled but no patchfile is present.  

## **What dependencies are needed or installed?**
*Developed under Bodhi 5.1 and tested on a Slax virtual machine so should work automatically on Ubuntu and Debian.  
Arch Fedora OpenSuSE confirmed working by users. Please test and report other distributions!*

Paste the command string recccommended below for your distribution directly into a terminal before running smlinux.  
*If your distribution is missing or needs packages not listed here, please let me know their names so I can update.*

**Fedora/Red Hat**

	sudo dnf install make gcc python3 audiofile-devel glew-devel SDL2-devel zstd zenity g++ newt unar p7zip-plugins
**openSuSE**

	sudo zypper in gcc make python3 glew-devel libSDL2-devel zenity libzstd-devel audiofile-devel
**Solus**
	
	sudo eopkg install make gcc python3 audiofile-devel glew-devel sdl2-devel zenity
**Void** 

	sudo xbps-install -S base-devel python3 audiofile-devel SDL2-devel glew-devel zstd zenity
**Alpine**

	sudo apk add build-base python3 audiofile-dev sdl2-dev glew-dev zenity
	
Some build targets depend on additional packages, for example Android builds require `android-sdk`, DOS targets require `djgpp`, web targets emscripten, sm64nx requires `g++` version 8 or newer, and using `sdl1` requires additional libraries, all of which smlinux only installs when those targets are specified.  Users of operating systems without advanced package tool may need to install the appropriate GCC/SDL/SDK/JDK with appropriate package manager.  

**macOS** If smlinux detects `Darwin` the following packages are installed with `brew`:

	libxdg-basedir coreutils git wget nano mingw-w64 gcc@9 sdl2 pkg-config glew glfw3 libusb audiofile unzip unrar newt go python3 PyQt5

**Windows** If smlinux detects `Msys` the following packages are installed with `pacman`:  
  	
	64-bit: mingw-w64-x86_64-python-pyqt5 mingw-w64-x86_64-python-numpy mingw-w64-x86_64-glew mingw-w64-x86_64-SDL2 mingw-w64-x86_64-gcc python3 python3-pip git make unzip zip unrar p7zip nano
	32-bit: mingw-w64-i686-python-pyqt5 mingw-w64-i686-python-numpy mingw-w64-i686-glew mingw-w64-i686-SDL2 mingw-w64-i686-gcc python3 python3-pip git make unzip zip unrar p7zip nano

**Ubuntu/Debian** If smlinux detects `apt`it is used to install the following packages:

	whiptail zenity git python3 python3-pip python3-pyqt5 wget unzip unrar p7zip-full build-essential bsdmainutils binutils libaudiofile-dev libglew-dev libsdl2-dev libusb-1.0-0-dev libzstd-dev mplayer

**Arch** Otherwise if smlinux detects `pacman` it is used to install the following packages:  

	 base-devel python audiofile sdl2 glew python-zstandard python-pip zstd zenity unzip zip unrar 

smlinux usually only installs these dependendencies automatically during the very first installation; if you wish to trigger installation again run:   
	
	smlinux depends

## **How do I create my rom file?**

Backup N64 cartridge with a dumper such as Retrode2 or Mr. Backup, from Wii with vcromclaim, or from Wii U Virtual Console with title dumper.  
[Dragonbox Store](https://www.dragonbox.de/en/accessories/cartridge-dumper/retrode2-with-all-plugins) &nbsp; [Stoneage Gamer](https://stoneagegamer.com/retrode-2-cart-reader-rom-dumper-for-super-nintendo-genesis-more.html) &nbsp; 
[Nintendo Wii U Store](https://www.nintendo.com/games/detail/super-mario-64-wii-u) &nbsp; [WiiU Title Dumper](https://gbatemp.net/threads/ddd-wiiu-title-dumper.418492) &nbsp; [Wii Virtual Console ROM Claim]( https://github.com/JanErikGunnar/vcromclaim)  
*Note that 3D All-Stars contains the Shindou version of the ROM which isn't fully supported by PC port.*  
## **How do I remove everything smlinux created during install?**
 
	smlinux purge
This erases files and folders created by smlinux including source repositories, add-ons, builds, icons, shortcuts, game saves and config files. This does not uninstall any dependencies installed with pip or your package manager.

## **How do I tell smlinux to download sm64 repositories to a folder other than home?**

	
Set `BASEPATH` to any existing directory that you have permission to write to, for example `BASEPATH=~/mario`.

	mkdir ~/mario
	smlinux config
