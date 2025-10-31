##  Instal Steps

Opted for DietPi because of its minimal overhead, with idle RAM consumption after installing Cockpit and Docker averaging around 300–400 MB

### 1. Flash DietPi to Each Node

1. Download the image:  
   [`DietPi_NativePC-BIOS-x86_64-Bookworm.img.xz`](https://dietpi.com/downloads/images/)

2. Make a live image bootable flash drive of any flavour of linux

4. Boot each **ZimaBlade** or **ZimaBoard** from the USB drive

5. Identify the internal storage device:
   ```bash
   lsblk -o NAME,SIZE,TYPE,MOUNTPOINT
   ```

Note: If you are using different devices, the process of flashing dietpi would be slightly different

For the zimaboards it looked something like this:
```bash
Name: 
├── SDA 57.3G disk <------ my boot flash drive
│   ├──sda1 57.3G PART / 
├── mccblk0 29.1G disk <------ Zimaboard/blade built in storage
│   ├── mccblk0p1 512M part 
│   ├── mmcvlk0p2 26.7G part 
│   ├── mmcblk0p3 1.9G part 
├── mmcblk0boot0 4M disk 
├── mmcblk0boot1 4MB
└──
```

6. After verifying the storage: Download and unzip the image
```bash
curl -L -o dietpi.img.xz https://dietpi.com/downloads/images/DietPi_NativePC-BIOS-x86_64-Bookworm.img.xz
unxz dietpi.img.xz
```
7. Flash it onto the Zimaboard/blade
```bash
dd if=dietpi.img of=/dev/mmcblk0 bs=4M status=progress conv=fsync
sync
poweroff
```
8. Remove USB and boot into fresh install of DietPi
