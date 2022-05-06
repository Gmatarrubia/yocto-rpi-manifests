 # Manifest files for building Linux images via Yocto

Setup packages for build

    sudo apt-get install gawk wget git-core diffstat unzip texinfo build-essential chrpath socat cpio python python3 pip3 pexpect libsdl1.2-dev xterm make xsltproc docbook-utils fop dblatex xmlto python-git libssl-dev pv

Install Google repo

    mkdir -p ~/.bin
    PATH="${HOME}/.bin:${PATH}"
    curl https://storage.googleapis.com/git-repo-downloads/repo > ~/.bin/repo
    chmod a+rx ~/.bin/repo
    export PATH=${PATH}:~/bin

### Raspberry Pi3 (32-bit)

```
export MACHINE=raspberrypi3
```

You may need to decrease setup-environment variable GPU_MEM to meet your specific needs.

### DRM

```
mkdir rpi_32_yocto && cd rpi_32_yocto
repo init -u https://github.com/jwinarske/manifests.git -m rpi32.xml -b honister
repo sync -j20
```
