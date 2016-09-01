# How To Install

1. compile QtermWidget & install

2. compile Qterminal

```bash
qmake
make
./Qterminal
```
## trouble shooting
you may have trouble as follows:
```bash
./QTerminal: error while loading shared libraries: libqtermwidget.so.0: cannot open shared object file: No such file or directory
```

In this case,
1. check the library is not found
```bash
ldd Qterminal |grep libqtermwidget.so.0 # return 'not found'
```
1. search the library file:
```bash
locate libqtermwidget.so.0 # /usr/local/lib64/libqtermwidget.so.0
```
1. add the path to config file.
```bash
cd /etc/ld.so.conf.d/
sudo touch Quantum.conf
sudo echo "/usr/local/lib64" > Quantum.conf # add path
sudo ldconfig
```


