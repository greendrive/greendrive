# Access GreenDrive Public Dataset

In GreenDrive, you can assign a mount point folder path to create a public dataset that appears as a folder located in a Windows or Linux system.
> Configuring a local proxy in the settings before using this feature is recommended to avoid unstable speed for Mainland China.

---
## Before you start
If you are a Windows user, ensure you have successfully installed WinFsp in the installation package: 
- path is **greendrive -> datasetfs -> winfsp-2.0.23075.msi**.

If you are a Linux user, ensure you have installed and configured the fuse when using Ubuntu as:
```
sudo apt update
sudo apt install libsnappy-dev libfuse-dev -y
echo "user_allow_other" | sudo tee -a /etc/fuse.conf
```

## Mount a dataset as a folder
1. Click **Public Dataset** on the left;
2. Create a path for the mount point folder;
3. Click the checkbox to choose the dataset ;
4. Click **Mount**.

![image](https://github.com/greendrive/greendrive/assets/150257109/7b91771f-2420-4091-9ec3-3855f7608df4)

The folder will be created on the assigned path. You can double-click on it to access its contents. You also have the option to access the dataset directly by using OS filesystem API.

## Unmount the dataset
When you finish using the dataset, you may want to unmount it.
Click the checkbox to choose the dataset ;
Click **Unmount**.

![image](https://github.com/greendrive/greendrive/assets/150257109/0d6ee7e1-6c3c-4b45-8e34-c391bdda55c7)

## Mount another dataset
You can mount up to one dataset at a time. Before mounting the new dataset, make sure to [unmount the previous dataset](#unmount-the-dataset) by following the steps mentioned above.



