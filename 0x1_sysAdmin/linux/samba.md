## MOUNT SAMBA SHARE
mount -t cifs //address/share /mount_point -o user=username password=pass		

sudo mount -t cifs //share_address/share /mount_point -o cred=credentials,user,auto