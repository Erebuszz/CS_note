> Noted by Erebuszz, modified on 5/6/2017

# Configure and apply BIOS Settings

## BIOS-BASIC INPUT/OUTPUT SYSTEM

### 1. Determine BIOS Version

There are two commands for checking the BIOS version on Windows

	> msinfo32
	> dxdiag

### 2. Find Update

Download the current and new versions

### 3. Secure Power

> On desktop computers or servers, 
> we use <b>UPS</b> (Uninterruptible Battery Supply)
> as a second source of electricity

### 4. Install BIOS

## Component Information

### CMOS battery :

> make a little bit backup energy to BIOS change, a round, silver-like things near the BIOS chip on the motherboard

Startup and press F2 or ESC…,depend on computer type, making model
	
### Information we’ll get from BIOS :

+ RAM
+ Hard drive
+ Optical Drive(CD drive…)
+ CPU(central processing unit)


## Configurations

### Use BIOS to change the boot order

1. Hard drive
2. CD
3. USB
4. PXE (network booting from server)

### Enable and disable devices

- I/O devices
- WOC (remotely turn on the computer)
- date / time
- CPU clock speeds
- Virtualisation (enable something like virtual box to use multiple OS)


## Diagnostics

### POST (Power On Self Test)

A set of instructions to test our compurter components<br>
 in an sequential order when we boot our computer 

1. CPU & POST BIOS ROM
2. system timer
3. video card
4. memory
5. keyboard
6. disk drives

> If one step goes wrong, it will completely stop and won’t pass it

* if we’ve got problems with POST, you can first check beeps on the motherboard, the beep code’s meaning depends on the manufacturer, it may show you the problems and status of Windows and BIOS processes. Or, we can use POST card plugged onto one of the PCI slots and turn on the computer, it will show what’s going on.

## Security

- A Supervisor & User password

In the situation when your computer was stolen
- tracking capabilities much like lo-jack called the Persistence Module (PM)
- Trusted Platform Module (TPM) which is a drive encryption function

# Differenciate Between Motherboards

## Motherboards

### Form Factors

1. ATX - Advanced Tech Extend

* 12 x 9.6 inches
* A rear port cluster for I/O ports
* 7 expansion slots<br> (run parallel to the short side of the motherboard)
* 6 slots total for memory
* Left side case opening<br>
 (as viewed from the front of a tower PC)

2. Micro-ATX

* 9.6 x 9.6 inches
* 4 expansion slots, 4 slots for memory

3. Mini-ITX

* 6.7 x 6.7 inches
* 1 PCI extension slot, for small-size desktop

## Input / Output Ports

![Image of ATX](https://computerhope.cachefly.net/bigmb.jpg)

> Memories are usually close to the CPU for the faster information communication