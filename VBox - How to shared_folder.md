1. Buat folder share di windows (Host). Misal dengan nama "shared_folder"
2. Login ke guest machine di vm, buat sebuah folder untuk mounting. Misal di bawah /mnt
	```bash
	# mkdir /mnt/shared_folder
	```
3. Buka virtual box, Pilih guest host -> Settings -> Shared Folders
	- Klik add new shared folder
	- browse ke folder yang diinginkan
	
		Misal : 
            
			Folder Path : D:\SOME DIREKTORI\shared_folder
            Folder Name : shared_folder
            Mount Point : /mnt/shared_folder/
            check "make permanent"
			
4. Masuk kembali ke guest machine, mount direktori share nya dengan syntax "mount -t vboxsf [FolderName] /path/to/mount".
	```bash
	# mount -t vboxsf shared_folder /mnt/shared_folder/
	```