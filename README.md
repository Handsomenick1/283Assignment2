# 283Assignment2

## Steps
Continue to use the Linux from Assignment1.

Install vm related packgages "sudo apt-get install qemu && sudo apt-get install qemu-kvm".

Go to */linux/arch/x86/kvm/cpuid.c* , add some code for the 0x4FFFFFFF and 0x4FFFFFFE, save it.

For Intel cpu, go to */linux/arch/x86/kvm/vmx/vmx.c*, add soem code for in the function `__vmx_handle_exit`, save it.

Call "sudo make -j cpu-core modules && make INSTALL_MOD_STRIP=1 modules_install" to rebuild and install your kernel.

Call "sudo reboot".

Search and download the corresponding os file.

You can use virt-manager install and run your nested vm, steps [here](https://www.how2shout.com/how-to/qemu-ubuntu-tutorial.html).

I run nested vm on qemu directly, stpes [here](https://techpiezo.com/linux/setup-virtual-machine-using-qemu-in-ubuntu/).

Inside of the nested vm, install cpuid package "sudo apt install cpuid"

Check the result by calling "cpuid -l 0x4FFFFFFF" and "cpuid -l -x4FFFFFFE".
