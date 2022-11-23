# Kernel Real-time 6.0.9 (tested: Ubuntu)

### Required
```
sudo apt install git wget build-essential bison flex libncurses-dev libssl-dev libelf-dev
```

### Clone github
```
git clone https://github.com/agoengwjy/kernel-rt.git
cd kernel-rt
```

### Download kernel
```
wget https://cdn.kernel.org/pub/linux/kernel/v6.x/linux-6.0.9.tar.xz
```

### Extract
```
tar xavf linux-6.0.9.tar.xz && cd ./linux-6.0.9
```

### Patch
```
patch -Np1 < ../patch-6.0.9-rt.patch
```

### Copy configuration
```
cp ../config .config
```

### Custome config if you want change config
```
make olddefconfig && make menuconfig
```

### Compile
```
make clean && make -j$(nproc) deb-pkg
```

### Installing
```
cd ..
sudo dpkg -i *.deb
```

