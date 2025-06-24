
#HOW TO CREATE AN EBS VOLUME
Ebs volume is like  a hard drive which is in block like structure
when attaching ebs, first we need to select subnet of the particular az like ap-south-1a,1b etc..
when attaching the created volume it will only attach to the volume present for a specific region
we can list down the block volume present on the webserver using cmd lsblk- list all block
when we want to use the created volume named like xvdf, we need to format it first using cmd----> mkfs.ext4 /dev/xvdf
xvdf will be shown when we list all block
here ext4 is a linux file system, dev- where the devices are present and xvdf is the device name
 use need to use sudo before the cmd to format, but in case you forgot about it then u can simple use sudo !!
 mkdir test
...> to mount a volume- mount /dev/xvdf /test/
 test is a folder where u want to mount
 to check if ur directory is mount the cmd is
 mountpoint /test
now whatever data u will store will be available in that folder
now the data we have created is present in the directory test
to unmount the volume cmd--> umount /test/
after un mount we will see in test directory that the data we have created is not present 
its like we have ejected a pendrive from the computer, laptop etc
we need to dettach the volume after the usage and delete the vol
 if you restart your instance the volume will be unmount
 
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
