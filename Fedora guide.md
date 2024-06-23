## extract tarballs in fedora
[useful links](https://docs.fedoraproject.org/en-US/quick-docs/installing-from-source/)
- to extract a .tar file use ``` tar -xf archive.tar (-xf means extract the tar file)```
- to extract a .tar.gz file use ```tar -zxf archive.tar.gz (-zxf means unzip and extract the tar file)```
- to extract a .gz file use ``` gzip -d archive.gz or $ gunzip archive.gz(-d means decompress and extract)```
- to extract a .zip file use ``` unzip archive.zip```

## enable fractional scaling in linux
```gsettings set org.gnome.mutter experimental-features "['scale-monitor-framebuffer']" ```
enter the command and reboot the system 

