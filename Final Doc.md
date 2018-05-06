# Final Project Documentation

## Building a Personal Network Attached Storage
This is the documentation for the final project of ETR 149. This document describes the process and issues encumbered by attempts at fulfilling the objective listed below.

## Objectives

To create a personal network attached storage (NAS) for use in a personal home environment using Openmediavault (OpenMV). The NAS will be accessible via local area network (LAN) and be able to contain data as manipulated by devices using it (clients). Each client should be allowed to access the NAS by a common method and be allowed to store data (such as backups) directly to the OpenMV.

## Findings

First on the board was research. I needed to know what type of NAS I needed and what type of hardware is required. I found Openmedia fault, which is a stand-alone storage server operating system (OS) based on Linux. I downloaded the iso file and worked on installing the new (OS).

### Installation

I had a standard desktop computer that I planned to convert into the server. However, all my attempts to install the OS to the hard drive failed.

The process of installing an iso file requires making the host media bootable, then copying the files to the drive. Making a drive bootable is not easy using a Linux host (I was using Ubuntu). I used a Windows machine and converted over the drive using command prompt to make the selected partitions on the drive “active.” I then transferred the files over to the hard disk and attempted to boot from it. Each time I received a boot-time error.

I tried switching the filesystem between EXT and FAT. Neither made a difference.

OpenMV had a very simplistic set of instructions on how ot make their OS bootable from a jump drive. There was little more instruction that what I already knew to do, and nothing was working yet.

I learned about a program called Etcher, which transfers isos to a USB or hard drive. This was successful for the USB, but did not work for my hard drive.

I tried booting from the USB, but again, received another boot-time error.

  

### Virtuosity

At this point, I turned to VirtualBox (VB). VB is a program for setting up and running operating systems in a virtual setting. It is perfect for testing and configuring operating systems in a controlled environment. VB had no issue installing OpenMV from the iso file.

Since now the operating system was function, I was time to set up some more OSs and test the NAS! I created a Windows 8.1, Windows 7, and an Ubuntu machine to see if each of them could connect. All that’s needed to get the machines networked is a few settings in VB.

## OpenMV

Openmediavault is remotely administrated via an interactive webpage. Although it is possible to configure everything inside the NAS OS, it is easier on the eyes and fingers to adjust and set everything via the web browser.

Setup was painful. In order to do anything, I needed to create shares. In order to create shares, I needed to create drives. And to create drives, I needed to configure each drive that OpenMV had access to (3, aside from the host’s hard disk).

### Shares
Next was setting up shares. Each share is set up on the OpenMV webpage as well as configured on the Windows and Linux clients. Once the share was made available, I needed to find it on the client’s OS.

On Windows, the share needs to be found by hitting run and punching in the network location of the share [\\OpenMV.local\](file://OpenMV.local/).

For Ubuntu, the process was similar. In their version of the file explorer, they have a section for a shared folder that’s auto-mounted. This issue with this, however, that for some reason, Ubuntu thought I didn’t have access to the folder. This caused by the user no being added to the OpenMV share privileges.

Now each OS has an extra folder that they can store files in or setup as part of a backup strategy.

### Features

OpenMV is not just for file sharing. It comes packed with advanced features and programs that are built for Windows and Linux. Some of which are:

- Each disk/logical disk mounted on the OpenMV machine can be set up in RAID configuration

- Task Scheduling (NAS side)

- SSH (Ubuntu)

- Synchronization

- ACLs

- Backup Management

  

# Conclusion

Once the project switched to virtual machines, progress was made. It was a massive time saver not having to worry about hardware/software compatibility. Some things I’ve taken away from this project are such:- OpenMV is a comprehensive operating system but is meant for advanced users who are already familiar with NAS software.

- OpenMV provides no method of installation apart from providing you an iso image of the OS. You’re left with the rest. Even the instructions for making the image bootable on a USB drive were either incomplete or unsuccessful.

- Nothing is completely automated. A big part of the configuration takes place on the client machines.

 - The access control list must be altered to allow access and use of shared folders.

- While SSH is wonderful, it is only available on Linux distros. It will need to be installed on most Windows machines.