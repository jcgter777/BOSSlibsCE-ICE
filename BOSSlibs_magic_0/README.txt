BOSshell CE libs for ICE by beckadamtheinventor, version 1.01.00 (magic edition)
These libraries are intended to supplement basic knowledge of 'ICE' compiler language, by Peter Tillemma ('PT_'), and are for use with this language. Yes, these libraries are open-source, as long as you reference the developer, beckadamtheinventor. These libraries may be edited at your own discretion/risk.
To use the libraries, simply 'include' them in the header of your program with this line of code: "AsmComp(BOSSLIBS", which automatically sets up the full-screen mode, closes all open files, and displays a 'splash-screen'.
Commands using 'Call' ('maxY' when ICE is not installed):
	CLS
	: clears the screen with the basic colour number BGC.
	TAC
	: sets the text colour to the basic colour number TAC.
	TBC
	: sets the text colour to the basic colour number TBC.
	TCC
	: sets the text colour to the basic colour number TCC.
	END
	: 'ends' the full-screen mode (goes back the the homescreen), and closes all open files.
	PRINT
	: puts a string on the screen. uses theta,L,TEXT,YMAX
	: YMAX is the maximum number of lines that you want this function to display.
	: L is the current output line
	: Uses YMAX
	: this will put string TEXT when on the full-screen mode.
	: If the calculator is still on the homescreen, it may crash!
	: Make sure to Preserve var L, or set it to change the next display line. The diplay line is in sets of 9 pixel rows.
	MENU
	: Does not print menu text, but provides a simple menu routine.
	: Vertical menu. uses Y,MAX,MIN,STEP
	: Uses Y as the starting point and minimum, MAX as the maximum, and STEP as the number of pixels per line.
	MENU2
	: Does not print menu text, but provides a simple menu routine.
	: 2-dimmensional Menu, useful for box-based setups. uses X,Y,XMIN,XMAX,YMIN,YMAX,XSTEP,YSTEP
	: Uses X and Y as the starting point and minimums, XMAX,YMAX as the maximum point, and XSTEP,YSTEP as the number of pixels per 'box'.
	2DMATC
	: Create Matrix filled with number A.
	: theta is the matrix letter prefix (0(A) to 9(J)), so AMATRIX to JMATRIX
	: X,Y is Matrix dimmensions, maximum X*Y==1600, so X and Y could be up to 40 if both are equal, more if they are not equal. This maximum is only needed to
	: keep from using too much memory.
	2DMATR
	: read index of matrix MATRIX at X,Y  which is just any matrix stored to MATRIX.
	2DMATW
	: write A to index of matrix MATRIX at X,Y  which is just any matrix stored to MATRIX.
NOTES on commands:
	: R==0 when action failed, R>0 when success.

Tips and Tricks:
	: Try using a list ('Data(','y' with a line over it, when ICE is not installed) as a string (in ICE only), and vice-versa.
	: Try changing the maximum matrix size by editing the library program: It is an unlocked program, so you can and may edit it!
	: To 'Preserve' a variable just means don't use it unless you have to for the use of the function.
