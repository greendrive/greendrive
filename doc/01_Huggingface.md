# Importing HuggingFace Project
Configuring a local proxy in the settings before using HuggingFace is recommended to avoid unstable speed for Mainland China.
## Function Description
We support resumes from breakpoint. If your download fails due to network fluctuation or block sealed timeout, you can click  **Pause All** first and then click **Start All** to resume from where you left off.

![image](https://github.com/greendrive/greendrive/assets/150257109/d353dc28-70dc-4812-a75b-0e949de62a12)

## Importing HuggingFace Models/Datasets
If you need to download a model/dataset that requires authorization or you need to be logged in to HuggingFace to download it, please [configure your HuggingFace account token](#configure-huggingface-account-token) as described in the following tutorial before downloading it.

Click on the HuggingFace button on the client page, enter the model/dataset link you want to download, and click **Browse** to access the list of related files. (NOTE: we use `https://huggingface.co/datasets/detection-datasets/coco` as example link)

![image](https://github.com/greendrive/greendrive/assets/150257109/3fb711e9-8e8f-43b7-9813-29bb52f51a5c)

You can select the files by clicking the checkbox to the left of the file name, and you can also select the individual files and click Batch Import to import them.

![image](https://github.com/greendrive/greendrive/assets/150257109/6dd858dd-8fed-4ea9-b9b6-98610820a73e)

You need to set the import path. For example, if imported to a **coco** folder, type **dataset/coco** and click **COMFIRM**.

![image](https://github.com/greendrive/greendrive/assets/150257109/d419210f-d6d4-40be-b49c-c2b1e0b13636)

After completing the above steps, you can monitor the upload progress of the files in real time by clicking on the **Uploading** button.

![image](https://github.com/greendrive/greendrive/assets/150257109/270be3a1-d533-4c06-997f-519e6bfa6cfb)

Once the upload is complete, you can view the relevant files in their respective folder.

![image](https://github.com/greendrive/greendrive/assets/150257109/9ab2c729-5ef8-46fa-9e66-776a57110e7e)

## Configure HuggingFace Account Token
Certain models/datasets on HuggingFace require authorization or login credentials to download, while others may require specific permissions. To download these models/datasets, you must first configure your HuggingFace account token. Without doing so, you will encounter the same error message as shown below when attempting to use the **Import HuggingFace Project** feature.

![image](https://github.com/greendrive/greendrive/assets/150257109/287f7797-a453-47da-87a7-946179b4ef3f)

After logging into HuggingFace, click on your avatar in the upper right corner and select Settings.
You can create a new token by following the steps: **Access Tokens -> New token**.

Enter the Token Name and select Role. The Name refers to the purpose of the Token, while the Role determines the Token permissions (the default one with read permissions can be enough). Click Generate a token to complete the creation process.

![image](https://github.com/greendrive/greendrive/assets/150257109/cfcaccd0-19ef-4d9e-9018-596fd97baad2)

After generating the token, click the Copy icon on the page to copy it.

![image](https://github.com/greendrive/greendrive/assets/150257109/03fc6de9-6dbb-4f72-aa6e-55815a0e08da)

In **GreenDrive**, click Settings located at the bottom left corner. Once you are on the Settings page, click the Settings button next to **HuggingFace Token**, and paste the copied Token to complete the step.

![image](https://github.com/greendrive/greendrive/assets/150257109/a6a46abf-e61e-47de-90ff-4804bfdf4a46)

After configuring the HuggingFace Token, you can load the models and datasets that require authentication.

![image](https://github.com/greendrive/greendrive/assets/150257109/e693b315-6d55-4199-8a4c-58e466ab9058)

## Note:
- Some models/datasets may require additional disk space. Please pay attention to the capacity of the disk.
- Some models/datasets need additional permissions (e.g. Llama2), please apply for relevant permissions on the HuggingFace website before downloading.

