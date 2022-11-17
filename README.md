# fedora-gnome-xorg-fractional-scaling
Xorg fractional scaling on Fedora Linux 37 and GNOME 43, patches taken from https://github.com/puxplaying/mutter-x11-scaling and https://github.com/puxplaying/gnome-control-center-x11-scaling

![gnome-control-center after installing](https://user-images.githubusercontent.com/58503327/202493611-d1cfcd4b-2d8d-452b-934c-681810fc7502.png)


## How to use
```
$ git clone https://github.com/th1nhhdk/fedora-gnome-xorg-fractional-scaling.git
$ cd fedora-gnome-xorg-fractional-scaling
$ cp -rv ./rpmbuild ~/
$ cd ~/rpmbuild/SPECS/
# dnf in -y rpm-build
# dnf builddep mutter.spec gnome-control-center.spec
$ rpmbuild --clean -ba mutter.spec
$ rpmbuild --clean -ba gnome-control-center.spec
$ cd ../RPMS/
# rpm --force -iv ./x86_64/mutter-43.0-4.fc37.x86_64.rpm ./noarch/gnome-control-center-filesystem-43.0-2.fc37.noarch.rpm ./x86_64/gnome-control-center-43.0-2.fc37.x86_64.rpm
# echo "exclude=mutter gnome-control-center-filesystem gnome-control-center" >> /etc/dnf/dnf.conf
```

## Using prebuilt binaries (Not Recommended)
- Download mutter-43.0-4.fc37.x86_64.rpm, gnome-control-center-filesystem-43.0-2.fc37.noarch.rpm and gnome-control-center-43.0-2.fc37.x86_64.rpm from Releases page
```
# rpm --force -iv ./mutter-43.0-4.fc37.x86_64.rpm ./gnome-control-center-filesystem-43.0-2.fc37.noarch.rpm ./x86_64/gnome-control-center-43.0-2.fc37.x86_64.rpm
# echo "exclude=mutter gnome-control-center-filesystem gnome-control-center" >> /etc/dnf/dnf.còn
```
