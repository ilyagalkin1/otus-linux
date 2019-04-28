    1  cd /
    2  cd etc/sysconfig/network-scripts/
    3  ls
    4  vi ifcfg-enp0s3 
    5  ls
    6  shutdown now
    7  yum update
    8  yum update -y
    9  shutdown now
   10  yum install git
   11  ls
   12  cd /
   13  ls
   14  git clone https://github.com/ilyagalkin1/otus-linux.git
   15  git tatus
   16  git status
   17  cd otus-linux/
   18  ls
   19  git status
   20  cd git_tutorial/
   21  ls
   22  cd work/
   23  ls
   24  git status
   25  mv test.txt  text.txt
   26  ls
   27  git status
   28  git add text.txt 
   29  vi text.txt 
   30  uname -r
   31  uname -a
   32  uname -r
   33  uname -r echo /otus-linux/git_tutorial/work/text.txt 
   34  echo uname -r  /otus-linux/git_tutorial/work/text.txt 
   35  cat text.txt 
   36  uname -r > /otus-linux/git_tutorial/work/text.txt 
   37  cat text.txt 
   38  uname -r > /otus-linux/git_tutorial/work/text.txt 
   39  cat text.txt 
   40  uname -a > /otus-linux/git_tutorial/work/text.txt 
   41  cat text.txt 
   42  uname -r
   43  uname -a
   44  cat text.txt 
   45  vi text.txt 
   46  cd /
   47  cd usr/src
   48  ls
   49  yum install wget
   50  wget https://cdn.kernel.org/pub/linux/kernel/v5.x/linux-5.0.9.tar.xz
   51  tar -Jxvf linux-5.0.9.tar.xz 
   52  ln -s linux-5.0.9/ linux
   53  ls -l
   54  rm -r linux-5.0.9.tar.xz 
   55  ls
   56  rm -r linux-5.0.9.tar.xz 
   57  ls
   58   yum groupinstall "Development Tools"
   59   yum groupinstall "Development Tools" -y
   60  yum install ncurses-devel hmaccalc zlib-devel binutils-devel elfutils-libelf-devel
   61  cd linux
   62  ls
   63  make mrproper
   64  make menuconfig
   65  make dep
   66  yum install openssl-devel bc
   67  make bzImage
   68  make modules
   69  make modules_install
   70  make install
   71  vi /etc/default/grub
   72  ls
   73  grub2-mkconfig -o /boot/grub2/grub.cfg
   74  uname -r
   75  reboot
   76  history
   77  history > /otus-linux/git_tutorial/work/text.txt 
   78  cat /otus-linux/git_tutorial/work/text.txt 
   79  find -name / .config
   80  find / -name .config
   81  shutdown now
   82  find / -name .config
   83  cd /usr/src/kernels/3.10.0-957.10.1.el7.x86_64.debug/
   84  ls
   85  ls -a
   86  cp .config  /otus-linux/git_tutorial/work/
   87  cd ..
   88  pwd
   89  cd /usr/src/linux
   90  ls
   91  ls -la
   92  ls -a
   93  cp .config  /otus-linux/git_tutorial/work/
   94  cp .config  /otus-linux/git_tutorial/work/.config2
   95  cd /otus-linux/git_tutorial/work/
   96  ls
   97  ls -a
   98  cat text.txt 
   99  git clone https://github.com/ilyagalkin1/otus-linux.git
  100  ls
  101  rm -rf otus-linux/
  102  git add text.txt .config .config2
  103  git commit -m "dz" -a
  104  git push
  105  cat /var/log/yum.log 
  106  git add text.txt 
  107  git status
  108  history
  109  cat /var/log/yum.log > /otus-linux/git_tutorial/work/text.txt 
  110  git commit -m "dz" -a
  111  git push
  112  yum update
  113  shutdown now
  114  ls
  115  shutdown now
  116  ssh test@192.168.1.61
  117  ls
  118  cd /
  119  df -h
  120  ip a
  121  ls
  122  cd /
  123  cd otus-linux/git_tutorial/work/
  124  ls
  125  ls -a
  126  cd ..
  127  ls
  128  cd .
  129  cd ..
  130  ls
  131  git init
  132  ls
  133  cd /
  134  ls
  135  rm -rf otus-linux/
  136  ls
  137  git clone https://github.com/ilyagalkin1/otus-linux.git
  138  git status
  139  cd otus-linux/
  140  ls
  141  git add README.md 
  142  history > README.md 
