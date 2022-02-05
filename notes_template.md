Machine Name:  
Machine IP:  
Exploit Port:  
Windows version:  
Vulnerable Application:  
Version:  
Public CVE:  
  
Overflow type:  
&nbsp;&nbsp;&nbsp;&nbsp;<ui> stack:</ui>  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;○ offset to overwrite EIP:  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;○ bad characters:  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;○ Amount of space following overwrite:  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;○ Address to JMP ESP:  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;○ DEP:  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;○ ASLR:  

&nbsp;&nbsp;&nbsp;&nbsp;<ui> SEH:</ui>  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;○ Offest to overwrite SEH:  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;○ Modules without SafeSEH:  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;○ Address to P/P/R:  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;○ short jump on NEH:  0x06eb9090  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;○ Bad characters:  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;○ Amount of space after SEH overwrite:  

 <ui>Egghunter:</ui>   
&nbsp;&nbsp;&nbsp;&nbsp;• Search string: w00tw00t  
&nbsp;&nbsp;&nbsp;&nbsp;• Address location:  
&nbsp;&nbsp;&nbsp;&nbsp;• Bad characters:  
&nbsp;&nbsp;&nbsp;&nbsp;• Amount of space:  
&nbsp;&nbsp;&nbsp;&nbsp;• Egghunter source:  
&nbsp;&nbsp;&nbsp;&nbsp;• Egghunter Assembly:  

<ui>Shellcode:</ui>  
&nbsp;&nbsp;&nbsp;&nbsp;• msfvenom command:  
&nbsp;&nbsp;&nbsp;&nbsp;• shell type:  
&nbsp;&nbsp;&nbsp;&nbsp;• custom shellcode:  
&nbsp;&nbsp;&nbsp;&nbsp;• listener command:  

Custom shellcode:  
&nbsp;&nbsp;&nbsp;&nbsp;• Requirements:  
&nbsp;&nbsp;&nbsp;&nbsp;• Additional functions or structures required:  
&nbsp;&nbsp;&nbsp;&nbsp;• Function prototypes:  
&nbsp;&nbsp;&nbsp;&nbsp;• Pseudo code outline:  
&nbsp;&nbsp;&nbsp;&nbsp;• reusable variables:  
&nbsp;&nbsp;&nbsp;&nbsp;• Stack offsets to store variables:  

DEP:  
&nbsp;&nbsp;&nbsp;&nbsp;• Modules without bad characters:  
&nbsp;&nbsp;&nbsp;&nbsp;• VirtualAlloc, VirtualProtect, or WriteProcessMemory:  
&nbsp;&nbsp;&nbsp;&nbsp;• Address or pointer to VA, VP, or WPM:  
&nbsp;&nbsp;&nbsp;&nbsp;• Known values that can be hard coded:  
&nbsp;&nbsp;&nbsp;&nbsp; [] • ROP template:   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;#VirtualAlloc  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;va  = struct.pack("<L", (0x45454545)) # dummy VirutalAlloc Address  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;va += struct.pack("<L", (0x46464646)) # Shellcode Return Address  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;va += struct.pack("<L", (0x47474747)) # # dummy Shellcode Address  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;va += struct.pack("<L", (0x48484848)) # dummy dwSize  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;va += struct.pack("<L", (0x49494949)) # # dummy flAllocationType  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;va += struct.pack("<L", (0x51515151)) # dummy flProtect  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;#Offset to control EIP  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;offset =offset to overwrite EIP  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;#EIP  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;eip =address to drop into buffer  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;# Patch VirtualAlloc  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;rop = address to gadget  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;# Patch Shellcode Return Address  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;rop += addressto next gadget  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;# Patch Shellcode lpAddress  
	  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;# Patch dwSize  
	  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;# Patch flAllocationType 0x1000  
	  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;# Patch flProtect  
  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;# Allign ESP to VirtualAlloc call  
  
ASLR:  
&nbsp;&nbsp;&nbsp;&nbsp;• DebugHelp, CreateToolhelp32Snapshot, EnumPrcessModules, fopen:  
&nbsp;&nbsp;&nbsp;&nbsp;• string format specifier:  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;○ printf, sprintf, vnsprintf:  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;○ %x:  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;○ %n:  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;○ Number of characters to leak address:  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;○ leaked module address:  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;○ leaked stack address:  
  
Reverse Engineering:  
&nbsp;&nbsp;&nbsp;&nbsp;• Listening ports:  
&nbsp;&nbsp;&nbsp;&nbsp;• Header format:  
&nbsp;&nbsp;&nbsp;&nbsp;• Checksum:  
&nbsp;&nbsp;&nbsp;&nbsp;• Opcodes:  
&nbsp;&nbsp;&nbsp;&nbsp;• Memory corruptions (scanf, scanf, memset, memcpy, strcpy):  
&nbsp;&nbsp;&nbsp;&nbsp;• Packet to trigger crash:  
&nbsp;&nbsp;&nbsp;&nbsp;• Packet to trigger info leak:  
&nbsp;&nbsp;&nbsp;&nbsp;• Command injection:  
  
PoC to crash:  
  
PoC to EIP control:  
  
PoC bad characters check:  
  
PoC ASLR:  
  
PoC DEP:  
  
Final PoC:  
  
Proof.txt:  
		  
