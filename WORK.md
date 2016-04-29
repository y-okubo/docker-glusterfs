# Login
```
ssh root@localhost -p 32769
```

# Create volume
```
mkdir /var/gfs_srv_vol
gluster peer probe $HOSTNAME
gluster volume create gfs_volume $HOSTNAME:/var/gfs_srv_vol force
gluster volume start gfs_volume
gluster volume quota gfs_volume enable
```

# Mount client
```
mkdir /var/gfs_cli_vol
mount -t glusterfs -o acl $HOSTNAME:/gfs_volume /var/gfs_cli_vol
```
# Install developer tool
```
yum groupinstall "Development Tools"
yum install vim
```
# GlusterFS API
http://enakai00.hatenablog.com/entry/20131130/1385895777

# ToDo
* マウントさせる
