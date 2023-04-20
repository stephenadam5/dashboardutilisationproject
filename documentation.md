Dashboard Utilisation Project:

<!--- Creating resources --->

To get started open the Azure Portal (https://portal.azure.com/) and create a resource group, for this example we'll call it 'DOCUMENTATIONdup'. Enter the relevant infomation regarding subscription and location.

![image](https://user-images.githubusercontent.com/81650373/233088669-bf0be979-15b5-41c4-a19e-07cdd3628f4e.png)

Hit 'create'.

Next create a Log Anaytics Workspace, Storage Account, Data Factory from the marketplace.

Your resource group should look like this:

![image](https://user-images.githubusercontent.com/81650373/233091033-c64204eb-59e5-4b6a-bc4b-020c40302865.png)

Now we have made our resources we need to configure them.

<!--- Creating AAD app & secrets --->

<!--- Configuring resources --->

Enter the storage account and go to 'Diagnostic settings > Add diagnostic setting', then 'Send to Log Analytics workspace'. Enable StorageRead, StorageWrite and StorageDelete. Your screen should look the same as:

![image](https://user-images.githubusercontent.com/81650373/233093083-f8c756a0-bcc6-4b2d-9a53-d7bbe00c01c9.png)

Hit 'save'.

Go into Data Factory and launch the studio, from here select 'New > Pipeline' to create a blank pipeline. Drag and drop two separate 'Web' task from the menu on the left alongside a single 'Copy data' task. Your Data Factory should now look like this:

![image](https://user-images.githubusercontent.com/81650373/233342175-8ba31520-9495-4dc3-aca5-88a2df706dcd.png)

Click on 'Web1' and go to 'Settings' at the bottom. From here enter the following information:

<ul>
  <li>URL: 'https://login.microsoftonline.com/[ENTER-SOMETHING-HERE]/oauth2/token'</li>
  <li>Method: 'POST'</li>
  <li>Body: 'grant_type=client_credentials&client_id=[YOUR-CLIENT-ID]&resource=https://api.loganalytics.io&client_secret=[ENTER-CLIENT-SECRET]'</li>
  <li>Authentication: 'None'</li>
  <li>Headers: name = 'Content-Type', value = 'application/x-www-form-urlencoded'</li>
  <li>Advanced: n/a</li>
</ul>
