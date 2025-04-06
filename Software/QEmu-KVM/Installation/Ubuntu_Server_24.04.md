# Ubuntu Server 24.04
Created Freitag 14 Juni 2024

Check virtualization hardware
-----------------------------
([Src](https://www.cyberciti.biz/faq/linux-xen-vmware-kvm-intel-vt-amd-v-support/))
# grep -E -wo '<List of flags with | separated>' /proc/cpuinfo  | sort | uniq
E.g. 64bit AMD or Intel virtualization?
# grep -E -wo 'lm|svm|vmx' /proc/cpuinfo  | sort | uniq
E.g. AMD virtualization?
# grep -E -wo 'lm|aes|svm|npt|lbrv|svm_lock|nrip_save|tsc_scale|vmcb_clean|flushbyasid|decodeassists|decodeassists|pausefilter|pfthreshol' /proc/cpuinfo  | sort | uniq
E.g. AMD virtualization?
# grep -E -wo 'lm|aes|vmx|ept|vpid|tpr_shadow|flexpriority|vnmi' /proc/cpuinfo  | sort | uniq

-> It's worth to execute both because some features are supported  by both.
### CPU flags
A [current list](https://git.kernel.org/pub/scm/linux/kernel/git/stable/linux.git/tree/arch/x86/include/asm/cpufeatures.h) for x86 cpus.
#### List of flags for virtualization
lm		You’ve 64 bit Intel or AMD cpu
aes		Applications performing encryption and decryption using the Advanced Encryption Standard on Intel and AMD cpus
##### Intel
vmx		Intel VT-x, virtualization support enabled in BIOS
ept		Intel extended page table support enabled to make emulation of guest page tables faster.
vpid		Intel virtual processor ID. Make expensive TLB flushes unnecessary when context switching between guests.
tpr_shadow
flexpriority	Intel feature that reduces calls into the hypervisor when accessing the Task Priority Register, which helps when running certain types of SMP guests.
vnmi		Intel Virtual NMI helps with selected interrupt events in guests

##### AMD
svm		AMD SVM, virtualization enabled in BIOS
npt		AMD Nested Page Tables, similar to Intel EPT.
lbrv		AMD LBR Virtualization support.
svm_lock	AMD SVM locking MSR.
nrip_save	AMD SVM next_rip save.
tsc_scale	AMD TSC scaling support.
vmcb_clean	AMD VMCB clean bits support.
flushbyasid	AMD flush-by-ASID support.
decodeassists	AMD Decode Assists support.
pausefilter	AMD filtered pause intercept.
pfthreshold	AMD pause filter threshold.

Installation qemu core
----------------------
Install the qemu packages:
``# apt install qemu-system``
or install a slim version with only necessary packages:
``# apt install qemu-system --no-install-recommends``


### Optional packages
This package can be help full.
qemu-utils	Tools qemu-img, qemu-io and qemu-nbd -> Usefull to create Qemu disk files.



