# Setup and Installations
1. Download VMWare Fusion and install it
2. Download the .iso file for Ubuntu version 18.04
3. Open VMWare, create a VM, and install Ubuntu OS on it. I did it with following specs:
    Memory: 5 GB, CPU Cores: 2, Disk: 120 GB
4. Install git
5. Fork the repository where the Kernel code is available and git clone the code from own repository
6. Go to the downloaded directory and install the necessary packages:
    
    `cd linux`
    
    `sudo apt-get update`
    
    `sudo apt-get install gcc, build-essential, flex, kernel-package fakeroot libncurses5-dev libssl-dev ccache bison`
7. Copy the .config<kernel-version> file from /boot to current directory and run command:
     
     `make oldconfig`
8. Select all the default answers and proceed. This will update the .config file with the latest configurations
9. Run the following command to build the kernel modules.

    `make -j <number of parallel processes>`
    
    Here, the number of parallel processes to run should be the number of cores assigned to the VM while creating it. In my case it was 2. The process took around 1.5 hours.
10. Build the kernel.
