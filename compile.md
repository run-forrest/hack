# Compiling the Android source code

It is well known that we should compile the source code to perform our tasks more efficiently and [easily.So](http://easily.So) let’s do it.Attention,we must use Ubuntu18.04 or later.

### 1.Configure requirements

the official requirements https://source.android.google.cn/docs/setup/start/requirements?hl=zh-cn

Before the set up,i recommend to use the VMware to compile the source code.

### 2.Install  required packages

`sudo apt-get install git-core gnupg flex bison build-essential zip curl zlib1g-dev libc6-dev-i386 x11proto-core-dev libx11-dev lib32z1-dev libgl1-mesa-dev libxml2-utils xsltproc unzip fontconfig
sudo apt-get update`

`sudo apt-get install curl git python3
sudo apt-get install repo`

`git config --global [user.name](http://user.name/) 'xxx'
git config --global user.email 'xxx@xxx.com'`

`mkdir ~/bin
PATH=~/bin:$PATH
curl https://mirrors.tuna.tsinghua.edu.cn/git/git-repo > ~/bin/repo (China only)
chmod +x ~/bin/repo`

`export REPO_URL='https://mirrors.tuna.tsinghua.edu.cn/git/git-repo/'`

`repo init -u https://aosp.tuna.tsinghua.edu.cn/platform/manifest -b android-13.0.0_r7`

`repo sync -c -j8`

`sudo apt-get install openjdk-11-jdk`

`sudo apt-get install git-core gnupg flex bison build-essential zip curl zlib1g-dev gcc-multilib g++-multilib libc6-dev-i386 libncurses5 lib32ncurses5-dev x11proto-core-dev libx11-dev lib32z1-dev libgl1-mesa-dev libxml2-utils xsltproc unzip fontconfig`

`source build/envsetup.sh`

### 3.Build the emulator

Since I need to use the emulator to run the project, I will compile the x86 version.

`lunch sdk_phone_x86_64-userdebug`

`make -j16`

Waiting for the long compilation process
