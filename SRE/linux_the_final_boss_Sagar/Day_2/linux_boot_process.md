when the power starts the BIOS/UEFI initiate test process called POST. (Power on self test).
BIOS/UEFI --> basic input/output system --> unified extensible firmware interface is modern replacement for BIOS with more features.(supports larger disks, faster boots, secure boots ,  graphical interface).
post -(power on self test) - It check readiness of basic hardware components (CPU, RAM, Keyboard, disk drivers, display adapters)
 if all tests pass then boot process will start. if fail then we will get error(no RAM detected)
  The fucntion of POST is to make sure system has minimum working hardware required to boot.

once post test successful means hardware is ready then control goes back to BIOD/UEFI
Then BIOS find bootable device(HDD, SSD, USB) which is having bootable disk inside it with valid boot sector and bootloader which is required to load linux OS kernel images & initramfs images into memory.
Bootable device is hardware
bootable disk is software. bootloader inside bootable disk responsible to load the OS.
bootloader sets CPU into correct mode (64 bit mode) and prepares registers. then CPU executes instructions directly from memory at the kernels entry points. as the CPU executes krenel instructions the kernel initializes hardware, memory and system process.
**VVIMP** kernel first uses initramfs (initial ram filesystem) a small temporary filesystem loaded into memory by bootloader. then kernel now access essentials drivers, modules, scripts stored inside initramfs.krenel detects real hardware using initramfs then kernel switch from initramfs to real root file-system
kernel starts systemd aslo called as PID1. systemd is responsible for managing all other processes and services. systemd reads unit files(/etc/systemd/system) and starts essential services , networking, logging, cron jobs. systemd identifies which services and targest to start.
systemd launches display manager which is responsible for login screen, user authentication, user desktop session. once authentication is successful the display manager starts user session. loading desktop environment. now GUI is fully available.



