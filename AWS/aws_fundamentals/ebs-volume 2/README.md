#DEATTACH AN EBS VOLUME FROM ONE INSTANCE AND ATTACH IT ANOTHER ONE

1. We will need to 2 instance for it
  first one is where we have mount all the volume and second just default instance	
2. Now the attach earlier volume to the new instance
3. now if you check the volume is present in new inst
4. check if data is present or not using sudo file -s /dev/xvdf
dev/xvdf: Linux rev 1.0 ext4 filesystem data, UUID=8afae0b1-09b3-4929-9502-0d67b32f33e6 (extents) (64bit) (large files) (huge files)
if u see the above op then we don't need to format it we have to just mount it
5. now create a folder mkdir /data
mount that-  mount /dev/xvdf /data
cd /data- you will see all the data of that previous volume
