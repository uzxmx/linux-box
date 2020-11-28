# linux-box

This box helps to experiment with a new linux kernel, build and install it.

The
new kernel will be the default menu entry of the grub boot loader.

> Note:
> The [Vagrantfile](Vagrantfile) is based on [my custom
> box](https://github.com/uzxmx/boxes/blob/master/mybox/Vagrantfile) which is based on
> Centos 7 box, so you can change the base box to Centos 7 and install
> software dependencies when needed.

## Quick start

**Boot up the VM**

The default kernel version is `5.7.6`. If you want to change to another version,
check and edit [Vagrantfile](Vagrantfile).

Run `vagrant up`. When VM is running, there will be a linux source directory in
the home directory.

**Build kernel**

```
cd /vagrant
./scripts/build_kernel
```

> Note: Every time you update the kernel source, you need to run
> `./scripts/build_kernel` to build and install kernel.

**Boot the new kernel by default**

```
cd /vagrant
sudo ./scripts/update_grub
```

> Note: This only needs to be run once.

## License

[MIT License](LICENSE)
