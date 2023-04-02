### Upgrade package dari slackpkg
```bash
     # slackpkg upgrade-all
```     
Atau download package dari situs resmi yang menyediakan patch kernel dari(lihat slackware.com)
Jika menggunakan metode download package, setelah selesai men-download package lalu upgrade kernal dengan syntax:
```bash
	# upgradepkg kernel-*.txz
```
	 
### Rebuild initrd

Ketikkan "getconf LONG_BIT" untuk melihat apakah sistemnya 32 bit atau 64 bit
a. untuk mesin 32 bit
```bash
# /usr/share/mkinitrd/mkinitrd_command_generator.sh -k 5.15.94-smp | bash
```
...b. untuk mesin 64 bit atau uniprocessor
```bash
# /usr/share/mkinitrd/mkinitrd_command_generator.sh -k 5.15.94 | bash
```
5.15.94 adalah versi kernel. Sesuaikan dengan versi kernel yang baru diinstall.
    
3. Konfigurasi Lilo (jika menggunakan Lilo)
Secara default, file Lilo.conf (/etc/lilo.conf) memiliki symlink yang selalu merujuk ke kernel yang tepat dan tidak perlu untuk mengedit file ini kecuali jika menggunakan lilo.conf yang telah di-kustomisasi.
Jika menggunakan file lilo yang telah di-kustomisasi, maka pastikan baris image= merujuk ke kernel yang tepat.
Jika menggunakan processor 32 bit atau uniprocessor, gunakan kernel versi 5.15.94-smp. Sedangkan mesin 64 bit selalu menggunakan versi 5.15.94.
    
4. Re-install Lilo
Baik anda merubah file lilo.conf (/etc/lilo.conf) maupun tidak, tetap harus melakukan re-install lilo
```bash
# lilo
```     
Atau untuk melihat perubahan apa yang dibuat secara penuh, jalankan syntax:
```bash
#lilo -v
```     
Jika ada warning yang ditampilkan namun tidak ada error, maka proses re-install lilo telah berhasil.
     
5.  Reboot
6.  Berdo'a.