**Заставить работать ls и cp см Видео выше. Вывод консоли в ответ.**

### Готовим cp
```sh
mkdir heraks heraks/bin heraks/lib heraks/usr heraks/usr/lib heraks/x86_64-linux-gnu heraks/lib/x86_64-linux-gnu
cp /bin/cp heraks/bin/
cp /bin/ls heraks/bin/
cp /lib/x86_64-linux-gnu/libselinux.so.1 heraks/lib
cp /usr/lib/x86_64-linux-gnu/libacl.so.1 heraks/lib
cp /usr/lib/x86_64-linux-gnu/libattr.so.1 heraks/lib
cp /lib/x86_64-linux-gnu/libc.so.6 heraks/lib
cp /lib/x86_64-linux-gnu/libpcre.so.3 heraks/lib
cp /lib/x86_64-linux-gnu/libdl.so.2 heraks/x86_64-linux-gnu/
cp /lib64/ld-linux-x86-64.so.2 heraks/lib64/
cp /lib/x86_64-linux-gnu/libpthread.so.0 heraks/lib
```
### cp запускается заебись
```sh
root@experemental:/# chroot heraks/
bash-5.0# cp
cp: missing file operand
Try 'cp --help' for more information.
bash-5.0#
```

### Готовим ls

```sh
ldd heraks/bin/cp
cp /lib/x86_64-linux-gnu/libselinux.so.1 heraks/lib/x86_64-linux-gnu/
cp /lib/x86_64-linux-gnu/libc.so.6 heraks/lib/x86_64-linux-gnu/
cp /lib/x86_64-linux-gnu/libpcre.so.3 heraks/lib/x86_64-linux-gnu/
cp /lib/x86_64-linux-gnu/libdl.so.2 heraks/lib/x86_64-linux-gnu/
cp /lib64/ld-linux-x86-64.so.2 heraks/lib64/
cp /lib/x86_64-linux-gnu/libpthread.so.0 heraks/lib/x86_64-linux-gnu/
```
### ls запускается заебись
```sh
root@experemental:/# chroot heraks/
bash-5.0# ls
bin  lib  lib64  usr  x86_64-linux-gnu
```