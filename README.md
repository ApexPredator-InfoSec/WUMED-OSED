# WUMED-OSED
Notes template for Offensive Security's EXP-301 course and OSED eaxm

This is the template I use to keep track of details while building an exploit or reverse engineering to find a vulnerability in a 32-bit Windows application. It was helpful for me during the EXP-301 course and OSED exam.


- Machine Name:
- Machine IP:
- Exploit Port:
- Windows version:
- Vulnerable Application:
- Version:
- Public CVE:

- Overflow type:
	- • stack:
		- • offset to overwrite EIP:
		- • bad characters:
		- • Amount of space following overwrite:
		- • Address to JMP ESP:
		- • DEP:
		- • ASLR:
	- •SEH:
		- ○ Offest to overwrite SEH:
		- ○ Modules without SafeSEH:
		- ○ Address to P/P/R:
		- ○ short jump on NEH:  0x06eb9090
		- ○ Bad characters:
		- ○ Amount of space after SEH overwrite:

Egghunter:
	• Search string: w00tw00t
	• Address location:
	• Bad characters:
	• Amount of space:
	• Egghunter source:
	• Egghunter Assembly:

Shellcode:
	• msfvenom command:
	• shell type:
	• custom shellcode:
	• listener command:

Custom shellcode:
	• Requirements:
	• Additional functions or structures required:
	• Function prototypes:
	• Pseudo code outline:
	• reusable variables:
	• Stack offsets to store variables:

DEP:
	• Modules without bad characters:
	• VirtualAlloc, VirtualProtect, or WriteProcessMemory:
	• Address or pointer to VA, VP, or WPM:
	• Known values that can be hard coded:
	• ROP template: 
	    #VirtualAlloc
	    va  = struct.pack("<L", (0x45454545)) # dummy VirutalAlloc Address
	    va += struct.pack("<L", (0x46464646)) # Shellcode Return Address
	    va += struct.pack("<L", (0x47474747)) # # dummy Shellcode Address
	    va += struct.pack("<L", (0x48484848)) # dummy dwSize
	    va += struct.pack("<L", (0x49494949)) # # dummy flAllocationType
	    va += struct.pack("<L", (0x51515151)) # dummy flProtect
	    #Offset to control EIP
	    offset =offset to overwrite EIP
	    #EIP
	    eip =address to drop into buffer
	    # Patch VirtualAlloc
	    rop = address to gadget
	    # Patch Shellcode Return Address
	   rop += addressto next gadget
	    # Patch Shellcode lpAddress
	
	    # Patch dwSize
	
	    # Patch flAllocationType 0x1000
	
	    # Patch flProtect
	
	    # Allign ESP to VirtualAlloc call

ASLR:
	• DebugHelp, CreateToolhelp32Snapshot, EnumPrcessModules, fopen:
	• string format specifier:
		○ printf, sprintf, vnsprintf:
		○ %x:
		○ %n:
		○ Number of characters to leak address:
		○ leaked module address:
		○ leaked stack address:

Reverse Engineering:
	• Listening ports:
	• Header format:
	• Checksum:
	• Opcodes:
	• Memory corruptions (scanf, scanf, memset, memcpy, strcpy):
	• Packet to trigger crash:
	• Packet to trigger info leak:
	• Command injection:

PoC to crash:

PoC to EIP control:

PoC bad characters check:

PoC ASLR:

PoC DEP:

Final PoC:

Proof.txt:
	
