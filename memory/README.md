# Memory layout

FF2E - FF2F    - program counter for 'G' (mikbug)?

E1FF - FFFF    - "do not use"

E1AC           - MIKBUG/SWTBUG INEEE, wait & input character to A
E1D1           - MIKBUG/SWTBUG OUTEEE, output A as character
E0E3           - MIKBUG/SWTBUG CONTRL, return to MIKBUG control
E0D0           - START, reset location
E0CA           - MIKBUG/SWTBUG OUT2HS, Output two hexadecimal characters and space (uses OUT2H)
E0C8           - MIKBUG/SWTBUG OUT4HS, Output four hexadecimal characters and a space (uses OUT2H)
E0BF           - MIKBUG/SWTBUG OUT2H, output two hexadecimal characters
E0AA           - MIKBUG/SWTBUG INHEX, Input hexadecimal digit, on error go to CONTRL
E07E           - MIKBUG/SWTBUG PDATA1, Print string pointed to by X, until EOT (0x04)
E078           - MIKBUG/SWTBUG INCH (=INEEE)
E075           - MIKBUG/SWTBUG OUTCH (=OUTEEE)
E068           - MIKBUG/SWTBUG OUTHR, Hexadecimal digit output from right nybble of byte in A 
E067           - MIKBUG/SWTBUG OUTHL, Hexadecimal digit output from left nybble of byte in A
E055           - MIKBUG/SWTBUG BYTE, hex input, two hex digits to byte A
E047           - MIKBUG/SWTBUG BADDR, build address, input 4 hex digits to X
E040           - SWTBUG/SWTBUG LOAD19
E000 - E3FF    - SWTBUG (if installed)
E000 - E1FF    - MIKBUG

C000 - DFFF    - unassigned (use for RAM or PROM, 8k bytes)
C000           - PROM location, jump here with 'Z'

B000 - BFFF    - unassigned (4k bytes)
A080 - AFFF    - unassigned (3968 bytes)

A04A - A07F    - available for scratch use
A048 - A049    - location for 'G' (goto) jump from swtbug
A047           - BYTECT - Temporary storage location for load/punch.
A046           - TEMP   - Temporary storage location for punch and load.
A044           - TW     - Temporary storage location for load/punch.
A042           - stack pointer when 'J' (jump) is called (programs should LDS #$ A042 at start)
A034 - A036    - available for scratch use (MIKBUG only, not available with SWTBUG)
A016           - BKLST  - Temporary data storage for the breakpoint routine.
A014           - BKPT   - Temporary breakpoint address storage
A014 - A033    - "available for scratch use" according to SWTBUG
A012 - A013    - SWIJMP - contains address for SWI (3F) interrupt handler
A010           - XTEMP  - temporary storage for I/O routines
A00E           - XLO    - temporary index register
A00D           - XHI    - temporary index register
A00C           - PORECH - tells SWTBUG whether or not to echo
A00A - A00B    - PORADD contains the I/O port address (8000 to 801C)
A008 - A009    - SP   - temporary storage for the stack pointer
A006 - A007    - NMI  - contains address for NMI interrupt handler
A004 - A005    - ENDA - contains msb/lsb of upper address for punching with 'P'
A002 - A002    - BEGA - contains msb/lsb of lower address for punching with 'P'
A000 - A001    - IRQ  - contains address for IRQ interrupt handler
A000 - A07F    - scratchpad RAM (MCM16810 on CPU board)

8020 - 8FFF    - unassigned (4064 bytes)

801C           - I/O port 7
8018           - I/O port 6
8014           - I/O port 5
8010           - I/O port 4
800C           - I/O port 3
8008           - I/O port 2
8004           - I/O port 1
8000           - I/O port 0
8000           - PIA address MCM6810

2000 - 2FFF    - MP-M at jumper position 2, etc
1000 - 1FFF    - MP-M at jumper position 1
0000 - 0FFF    - MP-M 4k RAM board at jumper position 0
0000 - 7FFF    - unassigned (32K bytes)


