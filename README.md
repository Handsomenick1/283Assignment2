# 283Assignment2

## Assignment2

- •For CPUID leaf node %eax=0x4FFFFFFF:
  - ◦Return the total number of exits (all types) in %eax
- •For CPUID leaf node %eax=0x4FFFFFFE:
  - ◦Return the high 32 bits of the total time spent processing all exits in %ebx
  - ◦Return the low 32 bits of the total time spent processing all exits in %ecx
    - ▪%ebx and %ecx return values are measured in processor cycles, across all VCPUs

## Steps

1.Continue to use the Linux from Assignment1.

2.Install vm related packgages "sudo apt-get install qemu && sudo apt-get install qemu-kvm".

3.Go to */linux/arch/x86/kvm/cpuid.c* , add some code for the 0x4FFFFFFF and 0x4FFFFFFE, save it.

4.For Intel cpu, go to */linux/arch/x86/kvm/vmx/vmx.c*, add soem code in the function `__vmx_handle_exit`, save it.

5.Call `sudo make -j cpu-core modules && sudo make INSTALL_MOD_STRIP=1 modules_install && sudo reboot` to rebuild, install and rebootkernel.

6.Search and download the corresponding os file.

7.You can use virt-manager install and run your nested vm, steps [here](https://www.how2shout.com/how-to/qemu-ubuntu-tutorial.html).

8.I ran nested vm on qemu directly, stpes [here](https://techpiezo.com/linux/setup-virtual-machine-using-qemu-in-ubuntu/).

9.Inside of the nested vm, install cpuid package "sudo apt install cpuid"

10.Check the result by calling `cpuid -l 0x4FFFFFFF` and `cpuid -l -x4FFFFFFE`.
