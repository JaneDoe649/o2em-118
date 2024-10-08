

                     O2EM v1.18 (Jan/2007)

                  an Odyssey 2 & Videopac+ emulator

      copyright 1996/1998 by Daniel Boris <dboris@comcast.net>
         
 Developed by Daniel Boris, Andre de la Rocha and Arlindo Oliveira
    
                 This package is released under the 
             Clarified Artistic License (see license.txt)
 
			 Project Homepage
                     http://o2em.sourceforge.net

---------------------------------------------------------------------------


O2EM is an open source Odyssey2 / Videopac console emulator, created by
Daniel Boris in 1996. Since version 0.80 it has been developed by AndrÈ de
la Rocha and since version 1.16 it has been developed by Arlindo M. de Oliveira.

This release includes the source code for O2EM v1.18 and binaries for
Windows. The sources probably can also be compiled under other platforms
that support the Allegro game library. The binary version for Linux/X11 and
DOS continues available just until the version 1.16. 

With the Windows binary, the latest stable version of the Allegro DLL is also
included. To use the Linux version you must get the Allegro library for Linux
yourself and install it as root. The DOS version does not need additional
files.

O2EM is a command line based program, but there are several Windows frontends
you can use. The "official" one is O2EM Launcher, created by Heitor
Barcellos.

In order to build O2EM from its sources, you need either the MingW or Cygwin
packages on Windows, DJGPP on DOS and GCC on Linux. See the links below.

The latest version of O2EM can be found at http://o2em.sourceforge.net If you
want to send bug reports, or be part of the O2EM development, go to the O2EM
project page at SourceForge : http://sourceforge.net/projects/o2em/



Useful links:

Dan Boris' home page: http://www.atarihq.com/danb/
Allegro library: http://alleg.sourceforge.net/
MingW C/C++ compiler: http://sourceforge.net/projects/mingw/
Soeren Gust page : http://soeren.informationstheater.de/
Odyssey2 Home: http://www.classicgaming.com/o2home/
Odysseymania the brazilian webpage : http://odysseymania.classicgaming.com.br
OdysseyBR Group: http://gamesource.groups.yahoo.com/group/OdysseyBR/
Videopac Forum: http://www.videopac.org

Acknowledgments:


We wish to thank the following people:
    
	Keita Iida (Keita/Pooka/Fygar)
	for his enthusiasm, for the O2EM beta testing, and general encouragement.

	Marco Kerstens (MarcoK)
	for providing Videopac schematics, and general support.

	Matthew Pritchard
	for sending some official O2 programming documents.

	Bo Krogsgaard (Therion23)
	for putting the idea of doing the emulator into my head to start with.

	Jason F. Gohlke
	for providing valuable Voice tech info as well as the voice samples.
        
	Soeren Gust : For sending his patches to O2EM and for technical
	information about the console. Part of his technical document was
	used to implement VP+ emulation.

	RenÈ van den Enden : for providing information about several
	unsupported games and other help.

	Simon Scudder : for sending technical information about the O2
	(including the datasheet of the VP+ gfx chipset), sampled sounds and
	his nice O2 disassembler.

	Heitor Barcellos : for creating the O2EM Launcher frontend.

	Marcelo Ribeiro : for the icon used with the windows version of O2EM,
	bug reports, and for information about O2 games.

	Rafael : for compiling a big list of bugs present in O2EM v0.87.

	Zimmerman : for sending his patch to add key customization, on which
	v1.00 customization was based.
	
	Arlindo de Oliveira : for sending patches to fix bugs in O2EM and for
	his interest in keeping the O2 emulation alive.
	
	The members of the OdysseyBR user group: for several bug reports, as
	well for support in general.

-----------------------------------------------------------------------------

Quick Setup:

To get O2EM up and running quickly follow these steps:

1. Unzip the O2EM archive on your hard drive, that will create the necessary 
   standard directories: ROMS, BIOS and VOICE into the main directory O2EM118.
2. Download the bios ROM O2ROM.BIN (or G7400.BIN, or C52.BIN, or JOPAC.BIN) 
   and put it into BIOS directory.
3. Download one or more game ROMs, for example KCMUNCH.BIN for KC Munchkin and
   put the ROM in ROMS directory.
4. From the O2EM118 directory type: o2em KCMUNCH.BIN to start the game.If wants
   to play KC Munchkin with BIOS VP+, type: o2em KCMUNCH.BIN -g7400 
   
---------------------------------------------------------------------------
Setup:

    Before you can run O2EM you need a copy of the Odyssey2 or Videopac bios
ROM. For copyright reasons, this ROM image can not be included in this
archive. This ROM image is stored inside the 8048 processor and can be read
out with the appropriate equipment. The image should be 1024 bytes long and
should be in the BIOS directory into the main directory O2EM118.

    You will also need cartridge images, but again for copyright reasons
these can not be provided. PLEASE DO NOT E-mail us asking for ROM images! All
messages asking for ROM images will be promptly deleted.

    If you wish to use Voice emulation for games like KC's Krazy Chase. 
Download the voice samples and unzip them into the VOICE directory
into the main directory O2EM118. There are two sets of voice samples, 
mainsamp.zip which is the main voice samples and sidsamp.zip which are the
samples used by the game Sid the Spellbinder. You only need the Sid samples
if you want voice in that game.

---------------------------------------------------------------------------


Usage:


o2em <file> [options]

<file> = file to load with extension


options:

-help	      Help display

-wsize=n      Window size used by the emulator (1=original, 2=double size, etc.)

-fullscreen   Use full screen mode

-scanlines    Enable scanlines use by the video emulation. Scanlines are a
              feature that makes your display look like a TV screen.

-nosound      Turn off sound emulation

-novoice      Turn off voice emulation

-svolume=n    Set sound volume (0-100)

-vvolume=n    Set voice volume (0-100)

-debug        Start the emulator in debug mode

-speed=n      Relative speed (100 = original speed)

-nolimit      Turn off speed limiter

-bios=file    Set the file name and directory to find the console
	      bios. By default it looks for a file named o2rom.bin.
       	      You can use a bios file from an Odyssey2, Videopac or
       	      Videopac+ console. If you want to run VP+ games (in 
	      VP+ mode) then you need a VP+ bios.

-romdir=path  Set the directory to find the game rom. By default it
	      looks for path named .../roms

-biosdir=path Set the directory to find the console bios. By default it
	      looks for path named .../bios

-o2rom        Start the emulator with Odyssey 2 bios (default for most games).

-c52          Start the emulator with french Odyssey 2 bios.

-g7400        Start the emulator with VP+ bios (default for detected VP+ only games).

-jopac        Start the emulator with french VP+ bios. 

-euro         This option enables the use of European timing / 50Hz mode.
              This option is usually not needed as most of the games that
              really require this mode will be auto-detected.

-filter       Enable the low-pass audio filter.

-scshot=file  Set the screen shot file name or template. The screen shot
              will be saved when you press the F8 key in the emulator.
              The extension of the file you give will set the file type.
              supported file types are bmp, pcx and tga. You can also give
              a template to save several files, using the @ character.
              Using an option like -scshot=dump@.bmp will save files with
              names like dump00.bmp, dump01.bmp, etc. The pictures will
              have a resolution of (320x240)*wsize.

-exrom        Enable the use of an alternative ROM mapping for 4Kb games, to
	      support some games that use a special 3kb program rom/1kb data
	      ROM mode. The only known that use it are Four in 1 Row and
	      Musician and both are detected by their CRC and set correctly.
	      So this option is to be used only with games that are currently
	      unknown to O2EM. Do not enable it as default, as it will make
	      all the 4kb games that do not use this special mode crash.
              
-s0=QUIT,PAUSE,DEBUG,RESET,SCREENCAP,SAVE,LOAD,INJECT_HIGH
	      These option defines which keys are used for some of the system 
	      keys, if you use this option, you have to enter all 8 keys, to 
	      override the original keys (ESC,F1,F4,F5,F8,F2,F3,F6)

-s1=mode/keys Define stick 1 mode/keys
-s2=mode/keys Define stick 2 mode/keys

              These options define how the console joysticks are emulated.
              You can use a joystick connected to your computer or use
              the keyboard. You can specify a mode number (compatible with
              previous versions of O2EM) to disable the joystick emulation,
              to select an actual joystick or to set a default keyboard
              emulation mode :
                0=Disable,
                1=Default Right keys (arrows keys and right shift)
                2=Default Left keys (W,S,A,D,SPACE)
                3=Joystick
              Example: -s1=1 -s2=3
                                 
              You can also specify a list of 5 keyboard codes that will
              be used to emulate the joystick, separated by comas
              (without spaces), using this order : UP,DOWN,LEFT,RIGHT,FIRE.
              The following codes are accepted (not case sensitive):
                A,B,C,D,E,F,G,H,I,J,K,L,M,N,O,P,Q,R,S,T,U,V,W,X,Y,Z,
                0, 1, 2, 3, 4, 5, 6, 7, 8, 9,
                0_PAD,1_PAD,2_PAD,3_PAD,4_PAD,5_PAD,6_PAD,7_PAD,8_PAD,9_PAD,
                TILDE, MINUS, EQUALS, BACKSPACE, TAB, OPENBRACE, CLOSEBRACE,
                ENTER, COLON, QUOTE, BACKSLASH, BACKSLASH2, COMMA, STOP,
                SLASH, SPACE, INSERT, DEL, HOME, END, PGUP, PGDN, LEFT,
                RIGHT, UP, DOWN, SLASH_PAD, ASTERISK, MINUS_PAD, PLUS_PAD,
                DEL_PAD, ENTER_PAD, PRTSCR, PAUSE, ABNT_C1, YEN, KANA, AT,
                CIRCUMFLEX, COLON2, KANJI, LSHIFT, RSHIFT, LCONTROL,
                RCONTROL, ALT, ALTGR, LWIN, RWIN, MENU, SCRLOCK, NUMLOCK
              Example: -s1=y,h,g,j,lcontrol -s2=8_PAD,5_PAD,4_PAD,6_PAD,RCONTROL

-scoreadr=address     where the high-score is saved for specific rom
-scoretype=type	      how the high-score is saved for specific rom
-score=highscore      default highscore on launch ("inject" with F6)
-scorefile=file	      file where the highscore is saved on exit

-savefile=file	      filename for save/load state

                   


----------------------------------------------------------------------------

Default configuration file:

O2EM now can use a configuration file to set the default options, so you can
specify your preferred options in this file, instead of typing it every time
you execute the emulator. The command line options override the default
settings in the file. This file must be called o2em_def.cfg and be in the
same directory of O2EM118. This configuration file is a text file where you can
put the same options you would use when calling O2EM by the command line, but
each option must be in a different line and you should not precede it with
the - character. You can also put comment lines in the file, starting the
line with the # character. Example configuration file:

    # My config
    wsize=3
    Euro
    scanlines
    filter
    g7400
    s1=8_pad,5_pad,4_pad,6_pad,rcontrol


You disable any option set in this file when you call O2EM in the command
line, passing the =0 parameter to the option. For this example configuration,
you could disable the filter option set in the file putting -filter=0 when
you call O2EM.


----------------------------------------------------------------------------

Controls:

    Arrow keys + L = Default joystick 1 emulation

    W,D,S,A + Space  = Default joystick 2 emulation

    ESC/F12 = Leave the emulator

    F1  = Pause/Information

    F2  = Save State-File

    F3  = Load State-File

    F4  = Enter debugger

    F5  = Reset emulator (same as pressing the reset on the O2 keyboard)

    F6  = Inject Highscore

    F8  = Make a screen shot

    Caps Lock = Enables/Disables the O2 keyboard input of the keys used by
    joystick emulation

----------------------------------------------------------------------------

Debugger:

The emulator comes with a built in debugger that was used for development.
The debugger is not very polished and fairly incomplete but it can be useful
for single stepping through programs and watching their behavior.

H = display help

----------------------------------------------------------------------------


