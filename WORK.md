mkdir /var/gfs_srv_vol
gluster peer probe $HOSTNAME
gluster volume create gfs_volume $HOSTNAME:/var/gfs_srv_vol force
gluster volume start gfs_volume
gluster volume quota gfs_volume enable

mkdir /var/gfs_cli_vol
mount -t glusterfs -o acl $HOSTNAME:/gfs_volume /var/gfs_cli_vol
