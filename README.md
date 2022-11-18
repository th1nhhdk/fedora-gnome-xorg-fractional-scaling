# fedora-gnome-xorg-fractional-scaling
Xorg fractional scaling on Fedora Linux 37 and GNOME 43, patches taken from https://github.com/puxplaying/mutter-x11-scaling and https://github.com/puxplaying/gnome-control-center-x11-scaling

![After installation screenshot](https://user-images.githubusercontent.com/58503327/202655092-7eff9828-589e-4d81-a061-d97ef68d19b9.png)

## How to install
- Download `mutter-43.0-4.fc37.src.rpm` and `gnome-control-center-43.0-2.fc37.src.rpm` from Releases page

```
# dnf in -y rpm-build
$ rpm -Uvh ./mutter-43.0-4.fc37.src.rpm ./gnome-control-center-43.0-2.fc37.src.rpm
$ cd ~/rpmbuild/SPECS
# dnf builddep mutter.spec
$ rpmbuild --clean -ba mutter.spec
# dnf builddep gnome-control-center.spec
$ rpmbuild --clean -ba gnome-control-center.spec
$ cd ~/rpmbuild/RPMS/
# rpm --force -iv ./x86_64/mutter-43.0-4.fc37.x86_64.rpm ./noarch/gnome-control-center-filesystem-43.0-2.fc37.noarch.rpm ./x86_64/gnome-control-center-43.0-2.fc37.x86_64.rpm
# echo "exclude=mutter gnome-control-center-filesystem gnome-control-center" >> /etc/dnf/dnf.conf
```

## or installing with `mock`
- Download `mutter-43.0-4.fc37.src.rpm` and `gnome-control-center-43.0-2.fc37.src.rpm` from Releases page

```
$ mock -r fedora-37-x86_64 ./mutter-43.0-4.fc37.src.rpm
$ cp -v /var/lib/mock/results/*.rpm .
$ mock -r fedora-37-x86_64 ./gnome-control-center-43.0-2.fc37.src.rpm
$ cp -v /var/lib/mock/results/*.rpm .
# rpm --force -iv ./x86_64/mutter-43.0-4.fc37.x86_64.rpm ./noarch/gnome-control-center-filesystem-43.0-2.fc37.noarch.rpm ./x86_64/gnome-control-center-43.0-2.fc37.x86_64.rpm
# echo "exclude=mutter gnome-control-center-filesystem gnome-control-center" >> /etc/dnf/dnf.conf
```

## Using prebuilt binaries (Not Recommended)
- Download `mutter-43.0-4.fc37.x86_64.rpm`, `gnome-control-center-filesystem-43.0-2.fc37.noarch.rpm` and `gnome-control-center-43.0-2.fc37.x86_64.rpm` from Releases page

```
# rpm --force -iv ./mutter-43.0-4.fc37.x86_64.rpm ./gnome-control-center-filesystem-43.0-2.fc37.noarch.rpm ./x86_64/gnome-control-center-43.0-2.fc37.x86_64.rpm
# echo "exclude=mutter gnome-control-center-filesystem gnome-control-center" >> /etc/dnf/dnf.conf
```
