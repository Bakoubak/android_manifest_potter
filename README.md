# **Repos needed to build Lineage OSS for Potter :**
https://github.com/Bakoubak/android_device_huawei_kirin710-9-common (in device/huawei/kirin710-9-common)  
https://github.com/Bakoubak/android_device_huawei_potter (in device/huawei/potter)  
https://github.com/Bakoubak/android_hardware_huawei (in hardware/huawei)  

## **Install those dependencies for Lineage Build:**
Debian : bc bison build-essential ccache curl flex g++-multilib gcc-multilib git
git-lfs gnupg gperf imagemagick lib32readline-dev lib32z1-dev libelf-dev liblz4-tool libsdl1.2-dev
libssl-dev libxml2 libxml2-utils lzop pngcrush rsync schedtool squashfs-tools xsltproc zip zlib1g-dev

## **Install/Update your repo version, uninstall the package from your package manager first (eg: sudo apt remove repo) and download from GoogleSources:**
sudo curl https://storage.googleapis.com/git-repo-downloads/repo > /usr/bin/repo  
sudo chmod a+x /usr/bin/repo

## **And obviously don't forget to clone your Lineage sources:**
mkdir Lineage-20 && cd Lineage-20  
repo init -u https://github.com/LineageOS/android.git -b lineage-20.0 --git-lfs --depth=1  
repo sync
