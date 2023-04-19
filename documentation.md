Dashboard Utilisation Project:

To get started open the Azure Portal (https://portal.azure.com/) and create a resource group, for this example we'll call it 'DOCUMENTATIONdup'. Enter the relevant infomation regarding subscription and location.

![image](https://user-images.githubusercontent.com/81650373/233088669-bf0be979-15b5-41c4-a19e-07cdd3628f4e.png)

Hit 'create'.

Next create a Log Anaytics Workspace, Storage Account, Data Factory from the marketplace.

Your resource group should look like this:

![image](https://user-images.githubusercontent.com/81650373/233091033-c64204eb-59e5-4b6a-bc4b-020c40302865.png)

Now we have made our resources we need to configure them.

Enter the storage account and go to 'Diagnostic settings > Add diagnostic setting', then 'Send to Log Analytics workspace'. Enable StorageRead, StorageWrite and StorageDelete. Your screen should look the same as:

![image](https://user-images.githubusercontent.com/81650373/233093083-f8c756a0-bcc6-4b2d-9a53-d7bbe00c01c9.png)

Hit 'save'.
