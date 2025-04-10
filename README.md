# Refactor for ESPNOW
It is my intention to add the ability to read DCC packets over EPSNOW. 
As packets will be sent in 'raw format' the use of this lib will allow the packets to be decoded. 
The changes should allow for wireless DCC packets to be sent to Locos / Accessories which are battery powered but using DCC decoders. 
It should mean that exisiting DIY DCC decoders using NmraDcc could use this version with very little, if any, changes to the code. 


# NmraDcc
NMRA Digital Command Control (DCC) Library

This library allows you to interface to a NMRA DCC track signal and receive DCC commands.

The library currently supports the AVR ATTiny84/85 & ATMega88/168/328/32u4 and Teensy 3.x using the INT0/1 Hardware Interrupt and micros() ONLY and no longer uses Timer0 Compare Match B, which makes it much more portable to other platforms.

**Warning** as of version 1.4.4 support has been removed for the following two call-back functions, which will cause your sketch to silently stop working:

	extern void notifyDccAccState( uint16_t Addr, uint16_t BoardAddr, uint8_t OutputAddr, uint8_t State )
	extern void notifyDccSigState( uint16_t Addr, uint8_t OutputIndex, uint8_t State) 



Developers:
   Use of the supplied git pre-commit hook is encouraged.  This will require installation of the 'astyle' package for formatting source file.
   See http://astyle.sourceforge.net for details on this package.

   On Linux or Mac development machines, run the following command after you clone the repository:

       ln -s support/pre-commit .git/hooks/pre-commit

   Reformatting the source code to the preferred style is easy using astyle.  Just run 'astyle --options=.astylerc NmraDcc.h NmraDcc.cpp'
