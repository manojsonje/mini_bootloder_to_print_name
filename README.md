# MINIMAL BOOTLOADER WHICH PRINTS MY NAME & ROLL NUMBER ON SCREEN	

>MCA ROLL NO :- 16155
>Name :- Manoj Devidas Sonje


## PLEASE FOLLOW GIVEN INSTRUCTIONS
To Show Name and Roll Number on booting screen from bootsector of secondary device. follow instructions. 
1 -  first step is to make iso image of bootcode i.e- bootloader run below command in terminal
           ```   nasm -f bin bootloader.asm -o bootloader.iso  ```
   we can also make bootloader.img by above command just by replacing bootloader.iso by bootloader.img
 
2 -  to check our iso is correct we should run bootloader.iso with help of qemu(vertual machine). to check 
       iso first ensure that qemu-system-x86_64 is installed .

3 -A] run below command to test our bootloader
        ```    qemu-system-x86_64 bootloader.iso         ```
      after running above command you will get screen shown above


   B]also we can use seconadary device to do this – first of all make secondary device bootable.

 
### Commands to make secondary device bootable(LINUX)
      
       ```  
            sudo umount /dev/sdX 
            sudo dd if=/path/to/boot.iso of=/dev/sdX bs=4M && sync 
       ```
where sdX is your usb device (this can be verified with lsblk).
The sync bit is important as dd can return before the write operation finishes.

