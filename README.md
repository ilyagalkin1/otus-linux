Script started on Tue May  7 19:20:24 2019
]0;root@otuslinux:/home/vagrant[?1034h[root@otuslinux vagrant]# parted
[?1034hGNU Parted 3.1
Using /dev/sda
Welcome to GNU Parted! Type 'help' to view a list of commands.
                                                                          (parted) select /dec[Kv/sdg
Using /dev/sdg
                                                                          (parted) 
                                                                          (parted) 
                                                                          (parted) print free
Error: /dev/sdg: unrecognised disk label
                                                                          Model: ATA VBOX HARDDISK (scsi)
Disk /dev/sdg: 8590MB
Sector size (logical/physical): 512B/512B
Partition Table: unknown
Disk Flags: 
                                                                          (parted) mklabel
                                                                          New disk label type? gpt
                                                                          (parted) print free
Model: ATA VBOX HARDDISK (scsi)
Disk /dev/sdg: 8590MB
Sector size (logical/physical): 512B/512B
Partition Table: gpt
Disk Flags: 

Number  Start   End     Size    File system  Name  Flags
        17.4kB  8590MB  8590MB  Free Space

                                                                          (parted) k[Kmkpart
                                                                          Partition name?  []? 
                                                                          File system type?  [ext2]? ext4
                                                                          Start? 500
                                                                          End? 550
Warning: The resulting partition is not properly aligned for best performance.
                                                                                                                                                    Ignore/Cancel? Ignore
                                                                          (parted) print
Model: ATA VBOX HARDDISK (scsi)
Disk /dev/sdg: 8590MB
Sector size (logical/physical): 512B/512B
Partition Table: gpt
Disk Flags: 

Number  Start  End    Size    File system  Name  Flags
 1      500MB  550MB  50.0MB

                                                                          (parted) printIgnore[3P55000ext4mkpart
                                                                          Partition name?  []? 
                                                                          File system type?  [ext2]? ext4
                                                                          Start? 550
                                                                          End? 0[K1000
Warning: The resulting partition is not properly aligned for best performance.
                                                                                                                                                    Ignore/Cancel? igno[K[K[K[KIgnore
                                                                          (parted) print
Model: ATA VBOX HARDDISK (scsi)
Disk /dev/sdg: 8590MB
Sector size (logical/physical): 512B/512B
Partition Table: gpt
Disk Flags: 

Number  Start  End     Size    File system  Name  Flags
 1      500MB  550MB   50.0MB
 2      550MB  1000MB  450MB

                                                                          (parted) print[K[K[K[K[KIgnore[2P1000[1P550ext4printIgnore[3P55000ext4mkpartprint free[4Pmkpart
                                                                          Partition name?  []? 
                                                                          File system type?  [ext2]? ext4[K[K[K[Kswap 
parted: invalid token: swap
                                                                          File system type?  [ext2]? ext2
                                                                          Start? 1000
                                                                          End? 1500
Warning: The resulting partition is not properly aligned for best performance.
                                                                                                                                                    Ignore/Cancel? Ignore
                                                                          (parted) print
Model: ATA VBOX HARDDISK (scsi)
Disk /dev/sdg: 8590MB
Sector size (logical/physical): 512B/512B
Partition Table: gpt
Disk Flags: 

Number  Start   End     Size    File system  Name  Flags
 1      500MB   550MB   50.0MB
 2      550MB   1000MB  450MB
 3      1000MB  1500MB  500MB

                                                                          (parted) printIgnore[2P1500000ext2swap [KIgnore[2P1000[1P550ext4printIgnore[3P55000ext4mkpartprint free[4Pmkpart
                                                                          Partition name?  []? 
                                                                          File system type?  [ext2]? ext4
                                                                          Start? 1500
                                                                          End? 2000
Warning: The resulting partition is not properly aligned for best performance.
                                                                                                                                                    Ignore/Cancel? Ignore
                                                                          (parted) 
                                                                          (parted) print
Model: ATA VBOX HARDDISK (scsi)
Disk /dev/sdg: 8590MB
Sector size (logical/physical): 512B/512B
Partition Table: gpt
Disk Flags: 

Number  Start   End     Size    File system  Name  Flags
 1      500MB   550MB   50.0MB
 2      550MB   1000MB  450MB
 3      1000MB  1500MB  500MB
 4      1500MB  2000MB  500MB

                                                                          (parted) mkpart 
                                                                          Partition name?  []? 
                                                                          File system type?  [ext2]? ext4
                                                                          Start? 2000
                                                                          End? 2500
Warning: The resulting partition is not properly aligned for best performance.
                                                                                                                                                    Ignore/Cancel? Ignore
                                                                          (parted) 
                                                                          (parted) 
                                                                          (parted) print
Model: ATA VBOX HARDDISK (scsi)
Disk /dev/sdg: 8590MB
Sector size (logical/physical): 512B/512B
Partition Table: gpt
Disk Flags: 

Number  Start   End     Size    File system  Name  Flags
 1      500MB   550MB   50.0MB
 2      550MB   1000MB  450MB
 3      1000MB  1500MB  500MB
 4      1500MB  2000MB  500MB
 5      2000MB  2500MB  500MB

                                                                          (parted) quit
Information: You may need to update /etc/fstab.

                                                                          ]0;root@otuslinux:/home/vagrant[root@otuslinux vagrant]# 
]0;root@otuslinux:/home/vagrant[root@otuslinux vagrant]# 
]0;root@otuslinux:/home/vagrant[root@otuslinux vagrant]# mkfs.ext4 /dev/sdg1
mke2fs 1.42.9 (28-Dec-2013)
Filesystem label=
OS type: Linux
Block size=1024 (log=0)
Fragment size=1024 (log=0)
Stride=0 blocks, Stripe width=0 blocks
12240 inodes, 48828 blocks
2441 blocks (5.00%) reserved for the super user
First data block=1
Maximum filesystem blocks=33685504
6 block groups
8192 blocks per group, 8192 fragments per group
2040 inodes per group
Superblock backups stored on blocks: 
	8193, 24577, 40961

Allocating group tables: 0/6   done                            
Writing inode tables: 0/6   done                            
Creating journal (4096 blocks): done
Writing superblocks and filesystem accounting information: 0/6   done

]0;root@otuslinux:/home/vagrant[root@otuslinux vagrant]# lsblk
NAME   MAJ:MIN RM   SIZE RO TYPE MOUNTPOINT
sda      8:0    0    40G  0 disk 
`-sda1   8:1    0    40G  0 part /
sdb      8:16   0   250M  0 disk 
sdc      8:32   0   250M  0 disk 
sdd      8:48   0   250M  0 disk 
sde      8:64   0   250M  0 disk 
sdf      8:80   0   250M  0 disk 
sdg      8:96   0     8G  0 disk 
|-sdg1   8:97   0  47.7M  0 part 
|-sdg2   8:98   0 429.2M  0 part 
|-sdg3   8:99   0 476.9M  0 part 
|-sdg4   8:100  0 476.9M  0 part 
`-sdg5   8:101  0 476.9M  0 part 
]0;root@otuslinux:/home/vagrant[root@otuslinux vagrant]# mdadm --create /dev/md0 --level=0 --raid=2 /dev/sdb /d ev/sdc
mdadm: Defaulting to version 1.2 metadata
mdadm: array /dev/md0 started.
]0;root@otuslinux:/home/vagrant[root@otuslinux vagrant]# lsblk
NAME   MAJ:MIN RM   SIZE RO TYPE  MOUNTPOINT
sda      8:0    0    40G  0 disk  
`-sda1   8:1    0    40G  0 part  /
sdb      8:16   0   250M  0 disk  
`-md0    9:0    0   496M  0 raid0 
sdc      8:32   0   250M  0 disk  
`-md0    9:0    0   496M  0 raid0 
sdd      8:48   0   250M  0 disk  
sde      8:64   0   250M  0 disk  
sdf      8:80   0   250M  0 disk  
sdg      8:96   0     8G  0 disk  
|-sdg1   8:97   0  47.7M  0 part  
|-sdg2   8:98   0 429.2M  0 part  
|-sdg3   8:99   0 476.9M  0 part  
|-sdg4   8:100  0 476.9M  0 part  
`-sdg5   8:101  0 476.9M  0 part  
]0;root@otuslinux:/home/vagrant[root@otuslinux vagrant]# lsblkmdadm --create /dev/md0 --level=0 --raid=2 /dev/sdb /deev/sdc[A[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C
[C[C[C[C[C[C[Ke[A[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C /dev[1P/sde[A[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[Cd /dev/sde[A[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C --raid=2 /dev/sdd /dev[1P/sde[A[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C1 --raid=2 /dev/sdd /dev/sde[A[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C --level=1 --raid=2 /dev/sdd /dev[1P/sde[A[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C1 --level=1 --raid=2 /dev/sdd /dev/sde[A[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C

mdadm: Note: this array has metadata at the start and
    may not be suitable as a boot device.  If you plan to
    store '/boot' on this device please ensure that
    your boot-loader understands md/v1.x metadata, or use
    --metadata=0.90
Continue creating array? yes
mdadm: Defaulting to version 1.2 metadata
mdadm: array /dev/md1 started.
]0;root@otuslinux:/home/vagrant[root@otuslinux vagrant]# mdadm --create /dev/md1 --level=1 --raid=2 /dev/sdd /deev/sde[K[K[K[K[K[K[A[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[K
[K[A[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[K[K[K[K[Ksdd[1P[1P[1P[1P[1P[1P[1@f[1@a[1@i[1@l[1P[1P[1P[1P[1P[1P[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[1P /dev/sdd[1P /dev/sdd[1P /dev/sdd[1P /dev/sdd[1P /dev/sdd[1P /dev/sdd[1P /dev/sdd[1P /dev/sdd[1P/dev/sdd[1P /dev/sdd[1P /dev/sdd[1P /dev/sdd[1P /dev/sdd[1P /dev/sdd[1P /dev/sdd[1P /dev/sddf /dev/sdda /dev/sddi /dev/sddl /dev/sdd
mdadm: set /dev/sdd faulty in /dev/md1
]0;root@otuslinux:/home/vagrant[root@otuslinux vagrant]# 
]0;root@otuslinux:/home/vagrant[root@otuslinux vagrant]# 
]0;root@otuslinux:/home/vagrant[root@otuslinux vagrant]# cat /proc/mdstat
Personalities : [raid0] [raid1] 
md1 : active raid1 sde[1] sdd[0](F)
      254976 blocks super 1.2 [2/1] [_U]
      
md0 : active raid0 sdc[1] sdb[0]
      507904 blocks super 1.2 512k chunks
      
unused devices: <none>
]0;root@otuslinux:/home/vagrant[root@otuslinux vagrant]# 
]0;root@otuslinux:/home/vagrant[root@otuslinux vagrant]# 
]0;root@otuslinux:/home/vagrant[root@otuslinux vagrant]# cat /proc/mdstatmdadm  /dev/md1 --fail /dev/sdd[15Pcat /proc/mdstat[Klsblk
NAME   MAJ:MIN RM   SIZE RO TYPE  MOUNTPOINT
sda      8:0    0    40G  0 disk  
`-sda1   8:1    0    40G  0 part  /
sdb      8:16   0   250M  0 disk  
`-md0    9:0    0   496M  0 raid0 
sdc      8:32   0   250M  0 disk  
`-md0    9:0    0   496M  0 raid0 
sdd      8:48   0   250M  0 disk  
`-md1    9:1    0   249M  0 raid1 
sde      8:64   0   250M  0 disk  
`-md1    9:1    0   249M  0 raid1 
sdf      8:80   0   250M  0 disk  
sdg      8:96   0     8G  0 disk  
|-sdg1   8:97   0  47.7M  0 part  
|-sdg2   8:98   0 429.2M  0 part  
|-sdg3   8:99   0 476.9M  0 part  
|-sdg4   8:100  0 476.9M  0 part  
`-sdg5   8:101  0 476.9M  0 part  
]0;root@otuslinux:/home/vagrant[root@otuslinux vagrant]# lsblkcat /proc/mdstatmdadm  /dev/md1 --fail /dev/sdd[1P /dev/sdd[1P /dev/sdd[1P /dev/sdd[1P /dev/sddr /dev/sdde /dev/sddm /dev/sddo /dev/sddv /dev/sdde /dev/sdd
mdadm: hot removed /dev/sdd from /dev/md1
]0;root@otuslinux:/home/vagrant[root@otuslinux vagrant]# mdadm  /dev/md1 --remove /dev/sdd[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[Clsblk[Kcat /proc/mdstatmdadm  /dev/md1 --fail /dev/sdd--create /dev/md1 --level=1 --raid=2 /dev/sdd /deev/sde[A[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[Clsblk[K
[K[A[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[Cmdadm --create /dev/md1 --level=1 --raid=2 /dev/sdd /deev/sde[A[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[Clsblk[K
[K[A[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C
NAME   MAJ:MIN RM   SIZE RO TYPE  MOUNTPOINT
sda      8:0    0    40G  0 disk  
`-sda1   8:1    0    40G  0 part  /
sdb      8:16   0   250M  0 disk  
`-md0    9:0    0   496M  0 raid0 
sdc      8:32   0   250M  0 disk  
`-md0    9:0    0   496M  0 raid0 
sdd      8:48   0   250M  0 disk  
sde      8:64   0   250M  0 disk  
`-md1    9:1    0   249M  0 raid1 
sdf      8:80   0   250M  0 disk  
sdg      8:96   0     8G  0 disk  
|-sdg1   8:97   0  47.7M  0 part  
|-sdg2   8:98   0 429.2M  0 part  
|-sdg3   8:99   0 476.9M  0 part  
|-sdg4   8:100  0 476.9M  0 part  
`-sdg5   8:101  0 476.9M  0 part  
]0;root@otuslinux:/home/vagrant[root@otuslinux vagrant]# lsblkmdadm  /dev/md1 --remove /dev/sdd[C[1P /dev/sdd[1P /dev/sdd[1P /dev/sdd[1P /dev/sdd[1P /dev/sdd[1P /dev/sdda /dev/sddd /dev/sddd /dev/sdd
mdadm: added /dev/sdd
]0;root@otuslinux:/home/vagrant[root@otuslinux vagrant]# mdadm  /dev/md1 --add /dev/sdd[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[Clsblk[Kmdadm  /dev/md1 --remove /dev/sdd[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[Clsblk[Kcat /proc/mdstatmdadm  /dev/md1 --fail /dev/sdd[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[C[15Pcat /proc/mdstat
Personalities : [raid0] [raid1] 
md1 : active raid1 sdd[2] sde[1]
      254976 blocks super 1.2 [2/1] [_U]
      [=================>...]  recovery = 87.3% (223360/254976) finish=0.0min speed=37226K/sec
      
md0 : active raid0 sdc[1] sdb[0]
      507904 blocks super 1.2 512k chunks
      
unused devices: <none>
]0;root@otuslinux:/home/vagrant[root@otuslinux vagrant]# cat /proc/mdstat
Personalities : [raid0] [raid1] 
md1 : active raid1 sdd[2] sde[1]
      254976 blocks super 1.2 [2/2] [UU]
      
md0 : active raid0 sdc[1] sdb[0]
      507904 blocks super 1.2 512k chunks
      
unused devices: <none>
]0;root@otuslinux:/home/vagrant[root@otuslinux vagrant]# lsblk
NAME   MAJ:MIN RM   SIZE RO TYPE  MOUNTPOINT
sda      8:0    0    40G  0 disk  
`-sda1   8:1    0    40G  0 part  /
sdb      8:16   0   250M  0 disk  
`-md0    9:0    0   496M  0 raid0 
sdc      8:32   0   250M  0 disk  
`-md0    9:0    0   496M  0 raid0 
sdd      8:48   0   250M  0 disk  
`-md1    9:1    0   249M  0 raid1 
sde      8:64   0   250M  0 disk  
`-md1    9:1    0   249M  0 raid1 
sdf      8:80   0   250M  0 disk  
sdg      8:96   0     8G  0 disk  
|-sdg1   8:97   0  47.7M  0 part  
|-sdg2   8:98   0 429.2M  0 part  
|-sdg3   8:99   0 476.9M  0 part  
|-sdg4   8:100  0 476.9M  0 part  
`-sdg5   8:101  0 476.9M  0 part  
]0;root@otuslinux:/home/vagrant[root@otuslinux vagrant]# ls
dz.md
]0;root@otuslinux:/home/vagrant[root@otuslinux vagrant]# 
]0;root@otuslinux:/home/vagrant[root@otuslinux vagrant]# 
]0;root@otuslinux:/home/vagrant[root@otuslinux vagrant]# 192.168.1.114s192.168.1.114c192.168.1.114p192.168.1.114 192.168.1.114d192.168.1.114z192.168.1.114.md192.168.1.114 192.168.1.114t192.168.1.114e192.168.1.114s192.168.1.114t192.168.1.114@192.168.1.114[C[C[C[C[C[C[C[C[C[C[C[C[C:
The authenticity of host '192.168.1.114 (192.168.1.114)' can't be established.
ECDSA key fingerprint is SHA256:bLkzesfxDdtbLmUTn5tAYOyt2vqSDfsfbkLraIuseVw.
ECDSA key fingerprint is MD5:e9:f7:ac:a6:9a:ea:73:dd:ab:02:31:ff:66:8a:8c:79.
Are you sure you want to continue connecting (yes/no)? yas  es
Warning: Permanently added '192.168.1.114' (ECDSA) to the list of known hosts.
test@192.168.1.114's password: 
dz.md                                           0%    0     0.0KB/s   --:-- ETAdz.md                                         100%