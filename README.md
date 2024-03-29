# **How to build Lineage OSS for P Smart 2019/Potter:**  

### **Install those dependencies for Lineage Build:**
Debian : bc bison build-essential ccache curl flex g++-multilib gcc-multilib git
git-lfs gnupg gperf imagemagick lib32readline-dev lib32z1-dev libelf-dev liblz4-tool libsdl1.2-dev
libssl-dev libxml2 libxml2-utils lzop pngcrush rsync schedtool squashfs-tools xsltproc zip zlib1g-dev

### **Install/Update your repo version, uninstall the package from your package manager first (eg: sudo apt remove repo) and download from GoogleSources:**
sudo curl https://storage.googleapis.com/git-repo-downloads/repo > /usr/bin/repo  
sudo chmod a+x /usr/bin/repo

### **And obviously don't forget to clone your Lineage sources:**
mkdir Lineage-20 && cd Lineage-20  
repo init -u https://github.com/LineageOS/android.git -b lineage-20.0 --git-lfs --depth=1  
repo sync

### **Repos needed to build Lineage OSS for Potter :**
**You can use roomservice to automate the retrieving of the repos:**  
curl https://raw.githubusercontent.com/Bakoubak/android_manifest_potter/Lineage-20/roomservice.xml > ./.repo/manifests/roomservice.xml

**Or if you prefer, you can clone every repos one by one:**  
https://github.com/Bakoubak/android_device_huawei_kirin710-9-common (in device/huawei/kirin710-9-common)  
https://github.com/Bakoubak/android_device_huawei_potter (in device/huawei/potter)  
https://github.com/Bakoubak/android_hardware_huawei (in hardware/huawei)  

### **Start build:**  
To start the build, use those commands:  
bash  
export USE_CCACHE=1  
export CCACHE_DIR=directory/of/your/ccache (This needs to have a lot of space left to store cache, so choose wisely)  
export CCACHE_EXEC=/usr/bin/ccache  
ccache -o compression=true  
source build/envsetup.sh  
breakfast lineage_potter-eng  
brunch lineage_potter-eng  
  
**And now wait until the build completes !**  
  
ls out/target/product/potter  
  
**Here is your Lineage build !**
