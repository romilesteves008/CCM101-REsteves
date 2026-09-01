# Checkpoint 7 – Linux Investigation

## Linux Server Information

### Operating System

I used the `cat /etc/os-release` command to identify the operating system of the Linux server.

**Result:**
PRETTY_NAME="Ubuntu 24.04.4 LTS"
NAME="Ubuntu"
VERSION_ID="24.04"
VERSION="24.04.4 LTS (Noble Numbat)"
VERSION_CODENAME=noble
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=noble
LOGO=ubuntu-logo

### CPU Information

I used the `lscpu` command to view the CPU information of the Linux server.

**Result:**
Architecture:                x86_64
  CPU op-mode(s):            32-bit, 64-bit
  Address sizes:             39 bits physical, 48 bits virtual
  Byte Order:                Little Endian
CPU(s):                      1
  On-line CPU(s) list:       0
Vendor ID:                   GenuineIntel
  BIOS Vendor ID:            Red Hat
  Model name:                Intel Xeon E312xx (Sandy Bridge, IBRS update)
    BIOS Model name:         RHEL-9.6.0 PC (Q35 + ICH9, 2009)  CPU @ 2.0GHz
    BIOS CPU family:         1
    CPU family:              6
    Model:                   42
    Thread(s) per core:      1
    Core(s) per socket:      1
    Socket(s):               1
    Stepping:                1
    BogoMIPS:                7008.00
    Flags:                   fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush mmx fxsr 
                             sse sse2 syscall nx rdtscp lm constant_tsc rep_good nopl xtopology cpuid tsc_known_freq p
                             ni pclmulqdq ssse3 cx16 pcid sse4_1 sse4_2 x2apic popcnt tsc_deadline_timer aes xsave avx
                              hypervisor lahf_lm cpuid_fault pti ssbd ibrs ibpb stibp tsc_adjust xsaveopt arat md_clea
                             r
Virtualization features:     
  Hypervisor vendor:         KVM
  Virtualization type:       full
Caches (sum of all):         
  L1d:                       32 KiB (1 instance)
  L1i:                       32 KiB (1 instance)
  L2:                        4 MiB (1 instance)
  L3:                        16 MiB (1 instance)
NUMA:                        
  NUMA node(s):              1
  NUMA node0 CPU(s):         0
Vulnerabilities:             
  Gather data sampling:      Not affected
  Indirect target selection: Mitigation; Aligned branch/return thunks
  Itlb multihit:             KVM: Mitigation: VMX unsupported
  L1tf:                      Mitigation; PTE Inversion
  Mds:                       Mitigation; Clear CPU buffers; SMT Host state unknown
  Meltdown:                  Mitigation; PTI
  Mmio stale data:           Unknown: No mitigations
  Reg file data sampling:    Not affected
  Retbleed:                  Not affected
  Spec rstack overflow:      Not affected
  Spec store bypass:         Mitigation; Speculative Store Bypass disabled via prctl
  Spectre v1:                Mitigation; usercopy/swapgs barriers and __user pointer sanitization
  Spectre v2:                Mitigation; Retpolines; IBPB conditional; IBRS_FW; STIBP disabled; RSB filling; PBRSB-eIB
                             RS Not affected; BHI Retpoline
  Srbds:                     Not affected
  Tsa:                       Not affected
  Tsx async abort:           Not affected
  Vmscape:                   Not affected

### Memory

I used the `free -h` command to check the memory available on the Linux server.

**Result:**
 total        used        free      shared  buff/cache   available
Mem:           1.9Gi       412Mi       870Mi       1.1Mi       788Mi       1.5Gi
Swap:          1.0Gi          0B       1.0Gi

### Disk Space

I used the `df -h` command to check the disk space of the Linux server.

**Result:**
Filesystem      Size  Used Avail Use% Mounted on
tmpfs           191M 1012K  190M   1% /run
/dev/vda1        19G  5.4G   13G  30% /
tmpfs           952M   84K  952M   1% /dev/shm
tmpfs           5.0M     0  5.0M   0% /run/lock
/dev/vda16      881M  117M  703M  15% /boot
/dev/vda15      105M  6.2M   99M   6% /boot/efi

## Cloud Migration

If this Linux server were migrated to the cloud, it could be hosted using virtual machine services from AWS, Microsoft Azure, and Google Cloud Platform. AWS provides Amazon EC2, Azure provides Azure Virtual Machines, and Google Cloud provides Compute Engine. These services can provide virtual servers where a Linux operating system and its applications can run.

## Screenshot

![KillerCoda Linux Terminal](screenshots/killercoda-terminal.png)

