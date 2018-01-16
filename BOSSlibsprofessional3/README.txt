BOSshell CE libs for ICE by beckadamtheinventor, version 1.02.03 (professional edition)
These libraries are intended to supplement basic knowledge of 'ICE' compiler language, by Peter Tillemma ('PT_'), and are for use with this language. Yes, these libraries are open-source, as long as you reference the developer, beckadamtheinventor. These libraries may be edited at your own discretion/risk.
Send file BOSSLIBP.8xp to your calculator. To use the libraries, simply 'include' them in the header of your program with this line of code: "AsmComp(BOSSLIBP", which automatically sets up the full-screen mode, closes all open files, and displays a 'splash-screen'.
Commands using 'Call' ('maxY' when ICE is not installed):
	SETUP
	: returns some data: BASIC colors ae in list COLORS, ICE keys A through theta are in list LETTERS (use indexes 0 (A) to 26 (theta) to get the key for that letter)
	END
	: 'ends' the full-screen mode (goes back the the homescreen), and closes all open files.
	MENU
	: Does not print menu text, but provides a simple menu routine.
	: sets text background color to basic color number BGC and foreground color to TAC
	: Vertical menu. uses Y,MAX,MIN,STEP
	: Uses Y as the starting point and minimum, MAX as the maximum, and STEP as the number of pixels per line. Returns Y as 0 if clear pressed, else returns line
	MENU2
	: Does not print menu text, but provides a simple menu routine.
	: sets text background color to basic color number BGC and foreground color to TAC
	: 2-dimmensional Menu, useful for box-based setups. uses X,Y,XMIN,XMAX,YMIN,YMAX,XSTEP,YSTEP
	: Uses X and Y as the starting point and minimums, XMAX,YMAX as the maximum points, and XSTEP,YSTEP as the number of pixels per 'box'
	: Returns X,Y as 0 if clear pressed, else X,Y as the cursor (box outline) position.
	2DMC
	: Create Matrix filled with number A.
	: theta is the matrix letter prefix (0(A) to 9(J)), so AMATRIX to JMATRIX
	: X,Y is Matrix dimmensions, maximum X*Y==1600, so X and Y could be up to 40 if both are equal, more if they are not equal. This maximum is only needed to
	: keep from using too much memory.
	2DMR
	: read index of matrix MATRIX at X,Y  which is just any matrix stored to MATRIX.
	2DMW
	: write A to index of matrix MATRIX at X,Y  which is just any matrix stored to MATRIX.
	IMGH
	: draw image from hex colors, uses list IDAT as image. Example: Data(1,Xsize,Ysize,image_data->IDAT
	: draws at X,Y and with scale factor XS,YS. Length X,Y is first two indexes of IDAT, rest is image data.
	IMGB
	: draw image from basic colors, must have initialized BASIC colors first, but you can setup these manually by assigning the list COLORS with the pallette you want to use, uses IDAT as image. ALSO: you need a space at the begginning so that ICE doesn't 'squish' the string to hex. Example: " 01011" would be a one-by-one sprite in blue. Goes up to "FFFF" (256*256)
	: draws at X,Y and with scale factor XS,YS. Length X,Y is first two indexes of IDAT, rest is image data.
	GIFH
	: draw 'gif' image sequence, uses list IDAT as image. Example: Data(1,Xsize,Ysize,Frames,image_data->IDAT where image_data has a length of Xsize*Ysize*Frames.
	: draws at X,Y and with scale factors XS,YS. Length X,Y is first two in dexes of IDAT, number of frames is third, rest is image data.
	INPUT
	: Input string at current cursor position. Clears a line on the screen from the cursor to X=320 (9 pixels) to the BASIC color number BGC. String I is the prompt, and String R is the input string, which has a number of characters in it equal to the maximum size of user input. 2nd selects the character set, del deletes a character, the alpha keys are the letters, and the number keys are the numbers. Should be self-explanatory, basically the same as classic BASIC input, exept on the full-screen mode.
	: You must call SETUP first.

NOT YET IMPLEMENTED:
	MACT
	: does math on a 3-byte-list of items in list DAT, with math stored as a string in ACT
	: String ACT syntax (commands may be put together in sequence, for the equations to be done in that order):
	: where "0" can be any number, and must have a space between math operations. Must have an "=" at the end of the string, but the space isn't needed at this point.
	: "+0", adds that number to the list.
	: "-0", subtracts that number from the list.
	: "*0", multiplies that number with the list.
	: "/0", divides that number from the list.
	: "R0", gets the remainder of that number from the list.

NOTES on commands:
	: R==0 when action failed, R>0 when success.

Tips and Tricks:
	: Try using a list ('Data(','y' with a line over it, when ICE is not installed) as a string (in ICE only), and vice-versa.
	: Try changing the maximum matrix size by editing the library program: It is an unlocked program, so you can and may edit it!
	: To 'Preserve' a variable just means don't use it unless you have to for the use of the function.