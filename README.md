# install_macosx_vm_linux

reference from https://techsviewer.com/install-macos-10-14-mojave-virtualbox-windows/

make sure virtualization is enabled in the bios

install oracle vm

install oracle extendions (need usb 3.0 support)

download iso (got to find on your own)

1) Open VirtualBox and at the top of the Window, click on the “new” button. This will open a wizard that will help you through the virtual machine creation process.

2) Throughout this process, you will be asked to provide various kinds of information. Provide the virtual machine name as macOS 10.14 Mojave and the type as Mac OS X. The version is macOS 10.14. Click on “continue” and on the next page, set the RAM to allocate to this time machine. The best choice is to choose RAM that is 50% to 65% of the whole RAM your computer has. This will enable the virtual machine to operate optimally.

3) Next, you will be required to specify the hard disk to use. Choose “use an existing virtual hard disk file” then open the “macOS Mojave 10.14.vmdk” file. Click on the “Finish” button and the virtual machine will be created.

4) Open the just created virtual machine and click on the “Settings” button. In the “System” category open the “motherboard” tab. Check the box next to “Enable EFI” and change chipset to IHC9 or PIIX3.

5) In the “Processor” tab, check the box next to “Enable PAE/NX” and increase cores to 2 (50% of your CPU)

6) In the “Display” category, change the Video memory to 128MB. You can make many other changes as you wish using the different categories available. When done, close the Virtual machine.

7) Open Storage tab then enables "Use Host I/O Cache" option.

8) In the "USB" category make sure you select USB 3.0

9) for linux: bash mac-vmtweak.sh 

   for windows: 
       Run Command Prompt
   
       Code for Virtualbox 5.x:
      
       cd "C:\Program Files\Oracle\VirtualBox\"
      
       VBoxManage.exe modifyvm "Your VM Name" --cpuidset 00000001 000106e5 00100800 0098e3fd bfebfbff
      
       VBoxManage setextradata "Your VM Name" "VBoxInternal/Devices/efi/0/Config/DmiSystemProduct" "iMac11,3"
      
       VBoxManage setextradata "Your VM Name" "VBoxInternal/Devices/efi/0/Config/DmiSystemVersion" "1.0"
      
       VBoxManage setextradata "Your VM Name" "VBoxInternal/Devices/efi/0/Config/DmiBoardProduct" "Iloveapple"
      
       VBoxManage setextradata "Your VM Name" "VBoxInternal/Devices/smc/0/Config/DeviceKey"                   
       
       "ourhardworkbythesewordsguardedpleasedontsteal(c)AppleComputerInc"
       
       VBoxManage setextradata "Your VM Name" "VBoxInternal/Devices/smc/0/Config/GetKeyFromRealSMC" 1       
       
       Replace "Your VM Name" with your Virtual Machine Name in step 3. 
       
       Close VirtualBox then copies this code to Command Prompt.

*might also have to play with readonly VM_RES="1680x1050"

10) Open the just created VirtualBox and click on the “Start” button. Create a new account.
