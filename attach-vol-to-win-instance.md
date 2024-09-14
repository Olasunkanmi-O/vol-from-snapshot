### Create an EC2 instance with windows server
1. Create an EC2 instance using windows AMI
![](./img/00.use-win-AMI.png)
2. Connect through RDP client
3. Connect to the instance using Remote Desktop Connection(RDC). If the localhost is running on windows OS, this can be found through the start menu. 
4. Copy the public DNS to the computer name on your RDC screen while the username will be the the same as shown in the instance setup
![](./img/002.connect.png)
5. In order to get the password, upload the .pem key (the public key of the keypair) used when launching the instance 
![](./img/003.decrypt%20password.png)
6. After decrypting the password, you will see your password on the 'connect page' of your instance
![](./img/004.password.png)
![](./img/03.windows-homepage.png)
7. At the side bar, click on volume and create a new volume, using General Purpose SSD, specify the size needed and the corresponding availability zone of your instance.
![](./img/04.create-vol.png)
8. The volume will become available which now needs to be attached
![](./img/05.attach-vol.png)
    - Specify the instance you wish to attach the volume to
    - choose a name for the volume and attach
9. AWS uses xvda as the primary disc, so one can use xvdb, xvdc etc
![](./img/06.choose-instance.png)
10. On the window server created, attach the volume.
![](./img/07.newdisc-online.png)
![](./img/08.initilize-disk.png)
![](./img/09.new-volume.png)
11. Create folders in the new volume attached to verify persistent data.
![](./img/11.create-folders.png)
12. On your aws console, go to volume, and create a snapshot of the attached volume
![](./img/10.create-snapshot.png)
13. Delete the volume that was attached.
![](./img/13.disk-delete.png)
![](./img/14.vol-delete.png)
14. Create new volume from the snapshot that was created in action 12. From the side menu, choose snapshot, then create volume from the particular snapshot
![](./img/15create-vol.png)
15. Attach the newly created volume to the windows instance and verify the folders that were created in the previous volume. The volume has been successfully restored 
![](./img/17attach-vol.png)
![](./img/17vol2.png)
![](./img/18.confirm.png)
16. Clear the resources used




