# !DAA - Digital Area Analysis
Digital Area Analysis for RISC OS

This is predominantly for archiving purposes. It has not been in development for the best part of 25 years.

Digital Area Analysis was an application for RISC OS that could work out areas from scanned maps, drawings, photos etc. It worked on a fairly simple principle - flood-fill the area required, count the number of pixels that comprise the fill, divide by the number of pixels that flood-fill a know area and the answer pops out.

It was mainly used by my father and I on roadworks his company did in the Highlands. The cross-sectional areas of the original and intended landscape would be provided. I'd scan these, process them through DAA to get the areas of land to be cut away or filled in, and he'd multipl this out to get the volume of soil, rock, aggregate etc for costing purposes. It was fast, accurate, and won him a lot of contracts.

This was a commercial product, but sold very few (a literal handful) of units. It was reviewed fairly favourably in the June 1998 issue (195) of Acorn User mangazine by Mike Cook. He noted that it was the kind of software thay might sell Acorn machines, but (quite rightly) panned the instruction manual. I'll scan this when I get chance.

It was written around the time of RISC OS 3/3.11, but I'm quite pleased to see that it still works on a Raspberry Pi running RISC OS. The version here is 2.60b, and will be how I left it when I switched my A5000 (where this came from) for a RiscPC. I believe the last version was 2.64, which I will upload as a release. This was the commercialised version (BasCrunch'd and Bas2App'd), and has an embarassingly weak serial number implementation method (back when I thought multiple EORs were incremental).

Development was in BBC BASIC V (using !Notepad) with a bit of in-built assembler that did the pixel counting. For efficiency/speed (it was fast back in the day, but running on modern hardware it's so fast you think it hasn't done anything) it requires 16-colour sprite files. There's an example within the application. I'll upload more when I get chance.

Speaking of development, looking back on it now there's a lot of things that are wrong/sub-optimal, and barely anything is commented - although most of the assembly is. Not sure why there are a few lines marked with a '?'.

That said, I'm still proud of it. I particularly like the way the toolbox attached to the main window behaves. It juts out to the left when the window size is less than the screen size, squeezes in when the window is moved towards the left, then finally 'locks' inside the main window if it's maximised or the left edge of the main window moves off screen.

To road test it:

Un-tar and run the app in RISC OS. Launch !Help for interactive help if required.
Shift-double-click the app to open its folder. Drag and drop the 'SCREEN' file onto the iconbar icon.
Click the 'calibrate' icon (open box with mouse pointer icon in it)
Enter a value for the known area, eg 9 (square metres) and click ok/press return
Double-click the open square in the bottom left of the image. It should turn blue.
Click either the orange or green paint can
Double-click any enclosed area in the image
Switch to the other paint can and repeat if required
Click the calculator icon for the results

It has other functionality - lines can be drawn for when flood fills 'escape' by right-clicking and dragging (holding shift while doing this draws white lines). Titles can be added, the image can be reloaded with/without keeping the results, and the processed image can be saved for reference.
