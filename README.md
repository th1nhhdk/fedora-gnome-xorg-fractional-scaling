# fedora-gnome-xorg-fractional-scaling
Xorg fractional scaling on Fedora Linux 37 and GNOME 43, patches taken from https://github.com/puxplaying/mutter-x11-scaling and https://github.com/puxplaying/gnome-control-center-x11-scaling

![gnome-control-center after installing](https://user-images.githubusercontent.com/58503327/202493611-d1cfcd4b-2d8d-452b-934c-681810fc7502.png)


## How to use
```
# dnf in -y rpm-build
$ cp -rv ./rpmbuild ~/
$ cd ~/rpmbuild/SPECS/
# dnf builddep mutter.spec gnome-control-center.spec
$ rpmbuild --clean -ba mutter.spec
$ rpmbuild --clean -ba gnome-control-center.spec
$ cd ../RPMS/
# rpm --force -iv ./x86_64/mutter-*.x86_64.rpm ./noarch/gnome-control-center-filesystem-*.noarch.rpm ./x86_64/gnome-control-center-*.x86_64.rpm
# echo "exclude=mutter gnome-control-center-filesystem gnome-control-center" >> /etc/dnf/dnf.conf
```
