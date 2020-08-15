# Azure Marketplace VM with CreateUIDefinition

![Azure Public Test Date](https://azurequickstartsservice.blob.core.windows.net/badges/100-marketplace-sample/PublicLastTestDate.svg)
![Azure Public Test Result](https://azurequickstartsservice.blob.core.windows.net/badges/100-marketplace-sample/PublicDeployment.svg)

![Azure US Gov Last Test Date](https://azurequickstartsservice.blob.core.windows.net/badges/100-marketplace-sample/FairfaxLastTestDate.svg)
![Azure US Gov Last Test Result](https://azurequickstartsservice.blob.core.windows.net/badges/100-marketplace-sample/FairfaxDeployment.svg)

![Best Practice Check](https://azurequickstartsservice.blob.core.windows.net/badges/100-marketplace-sample/BestPracticeResult.svg)
![Cred Scan Check](https://azurequickstartsservice.blob.core.windows.net/badges/100-marketplace-sample/CredScanResult.svg)

[![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2F100-marketplace-sample%2Fazuredeploy.json)  [![Visualize](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/visualizebutton.svg?sanitize=true)](http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2F100-marketplace-sample%2Fazuredeploy.json)



This template allows deploying a linux VM using new or existing resources for the Virtual Network, Storage and Public IP Address.  It also allows for choosing between SSH and Password authentication.  The templates uses conditions and logic functions to remove the need for nested deployments. 

This template contains extra parameters to allow for the existing resources use cases, which is a common scenario for Azure Applications in the Azure Marketplace.

createUiDefinition.json is also included.

Before submitting to Marketplace, the following steps will need to be performed

- Rename ```azuredeploy.json``` to ```mainTemplate.json```
- Remove ```azuredeploy.parameters.json``` from the list of files to be submitted
- Update the GUID in ```mainTemplate.json``` for Customer Usage Attribution

Create a GUID for your application: https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR3i8TQB_XnRAsV3-7XmQFpFUMVRVVFFLTDFLS0E2QzNYSkFZR1U3WVJCTSQlQCN0PWcu

Enter the GUID value after the pid- prefix in the ```name``` field of the ```Microsoft.Resources/deployments``` resource
e.g. pid-eb7927c8-dd66-43e1-b0cf-c346a422063
  - https://docs.microsoft.com/en-us/azure/marketplace/marketplace-solution-templates

- Create a zip package of all the dependencies including the templates files, scripts, UI definition etc
  - https://docs.microsoft.com/en-us/azure/marketplace/cloud-partner-portal/azure-applications/cpp-skus-tab#package-details-for-solution-template 
  
  `Tags: new, exiting, resource, vm, condition, conditional`



# Validating the Template from your desktop

- Open a Powershell window
- Install-Module AzureRM
- Install-Module -Name AzureRM.Resources 
-  Install-Module -Name  Azure.Storage 
- Connect-AzureRmAccount
- .\Deploy-AzureResourceGroup.ps1 -ArtifactStagingDirectory complianceapp -ResourceGroupLocation eastus -UploadArtifacts -ValidateOnly 
 



Output from the validation of the script:
 Using template file:  complianceapp\azuredeploy.json
Using parameter file: complianceapp.\azuredeploy.parameters.json
Running a ResourceGroup scoped deployment...


ResourceGroupName : ARM_Deploy_Staging
Location          : eastus
ProvisioningState : Succeeded
Tags              : 
ResourceId        : /subscriptions/6ebd2f8c-21d7-4e7c-a99c-2673781552f6/resourceGroups/ARM_Deploy_Staging


CloudBlobContainer : Microsoft.WindowsAzure.Storage.Blob.CloudBlobContainer
Permission         : Microsoft.WindowsAzure.Storage.Blob.BlobContainerPermissions
PublicAccess       : Off
LastModified       : 8/15/2020 7:18:49 PM +00:00
ContinuationToken  : 
Context            : Microsoft.WindowsAzure.Commands.Storage.AzureStorageContext
Name               : complianceapp-stageartifacts


ICloudBlob                         : Microsoft.WindowsAzure.Storage.Blob.CloudBlockBlob
BlobType                           : BlockBlob
Length                             : 13307
IsDeleted                          : False
RemainingDaysBeforePermanentDelete : 
ContentType                        : application/octet-stream
LastModified                       : 8/15/2020 7:18:49 PM +00:00
SnapshotTime                       : 
ContinuationToken                  : 
Context                            : Microsoft.WindowsAzure.Commands.Storage.AzureStorageContext
Name                               : azuredeploy.json


ICloudBlob                         : Microsoft.WindowsAzure.Storage.Blob.CloudBlockBlob
BlobType                           : BlockBlob
Length                             : 326
IsDeleted                          : False
RemainingDaysBeforePermanentDelete : 
ContentType                        : application/octet-stream
LastModified                       : 8/15/2020 7:18:49 PM +00:00
SnapshotTime                       : 
ContinuationToken                  : 
Context                            : Microsoft.WindowsAzure.Commands.Storage.AzureStorageContext
Name                               : azuredeploy.parameters.json


ICloudBlob                         : Microsoft.WindowsAzure.Storage.Blob.CloudBlockBlob
BlobType                           : BlockBlob
Length                             : 8885
IsDeleted                          : False
RemainingDaysBeforePermanentDelete : 
ContentType                        : application/octet-stream
LastModified                       : 8/15/2020 7:18:50 PM +00:00
SnapshotTime                       : 
ContinuationToken                  : 
Context                            : Microsoft.WindowsAzure.Commands.Storage.AzureStorageContext
Name                               : createUiDefinition.json


ICloudBlob                         : Microsoft.WindowsAzure.Storage.Blob.CloudBlockBlob
BlobType                           : BlockBlob
Length                             : 780
IsDeleted                          : False
RemainingDaysBeforePermanentDelete : 
ContentType                        : application/octet-stream
LastModified                       : 8/15/2020 7:18:50 PM +00:00
SnapshotTime                       : 
ContinuationToken                  : 
Context                            : Microsoft.WindowsAzure.Commands.Storage.AzureStorageContext
Name                               : metadata.json


ICloudBlob                         : Microsoft.WindowsAzure.Storage.Blob.CloudBlockBlob
BlobType                           : BlockBlob
Length                             : 2746
IsDeleted                          : False
RemainingDaysBeforePermanentDelete : 
ContentType                        : application/octet-stream
LastModified                       : 8/15/2020 7:18:50 PM +00:00
SnapshotTime                       : 
ContinuationToken                  : 
Context                            : Microsoft.WindowsAzure.Commands.Storage.AzureStorageContext
Name                               : README.md


ICloudBlob                         : Microsoft.WindowsAzure.Storage.Blob.CloudBlockBlob
BlobType                           : BlockBlob
Length                             : 1175
IsDeleted                          : False
RemainingDaysBeforePermanentDelete : 
ContentType                        : application/octet-stream
LastModified                       : 8/15/2020 7:18:50 PM +00:00
SnapshotTime                       : 
ContinuationToken                  : 
Context                            : Microsoft.WindowsAzure.Commands.Storage.AzureStorageContext
Name                               : assets/hero.png


ICloudBlob                         : Microsoft.WindowsAzure.Storage.Blob.CloudBlockBlob
BlobType                           : BlockBlob
Length                             : 397
IsDeleted                          : False
RemainingDaysBeforePermanentDelete : 
ContentType                        : application/octet-stream
LastModified                       : 8/15/2020 7:18:50 PM +00:00
SnapshotTime                       : 
ContinuationToken                  : 
Context                            : Microsoft.WindowsAzure.Commands.Storage.AzureStorageContext
Name                               : assets/large.png


ICloudBlob                         : Microsoft.WindowsAzure.Storage.Blob.CloudBlockBlob
BlobType                           : BlockBlob
Length                             : 315
IsDeleted                          : False
RemainingDaysBeforePermanentDelete : 
ContentType                        : application/octet-stream
LastModified                       : 8/15/2020 7:18:50 PM +00:00
SnapshotTime                       : 
ContinuationToken                  : 
Context                            : Microsoft.WindowsAzure.Commands.Storage.AzureStorageContext
Name                               : assets/medium.png


ICloudBlob                         : Microsoft.WindowsAzure.Storage.Blob.CloudBlockBlob
BlobType                           : BlockBlob
Length                             : 193
IsDeleted                          : False
RemainingDaysBeforePermanentDelete : 
ContentType                        : application/octet-stream
LastModified                       : 8/15/2020 7:18:51 PM +00:00
SnapshotTime                       : 
ContinuationToken                  : 
Context                            : Microsoft.WindowsAzure.Commands.Storage.AzureStorageContext
Name                               : assets/small.png


ICloudBlob                         : Microsoft.WindowsAzure.Storage.Blob.CloudBlockBlob
BlobType                           : BlockBlob
Length                             : 453
IsDeleted                          : False
RemainingDaysBeforePermanentDelete : 
ContentType                        : application/octet-stream
LastModified                       : 8/15/2020 7:18:51 PM +00:00
SnapshotTime                       : 
ContinuationToken                  : 
Context                            : Microsoft.WindowsAzure.Commands.Storage.AzureStorageContext
Name                               : assets/wide.png


ICloudBlob                         : Microsoft.WindowsAzure.Storage.Blob.CloudBlockBlob
BlobType                           : BlockBlob
Length                             : 846
IsDeleted                          : False
RemainingDaysBeforePermanentDelete : 
ContentType                        : application/octet-stream
LastModified                       : 8/15/2020 7:18:51 PM +00:00
SnapshotTime                       : 
ContinuationToken                  : 
Context                            : Microsoft.WindowsAzure.Commands.Storage.AzureStorageContext
Name                               : scripts/copyfilefromazure.sh


ICloudBlob                         : Microsoft.WindowsAzure.Storage.Blob.CloudBlockBlob
BlobType                           : BlockBlob
Length                             : 64
IsDeleted                          : False
RemainingDaysBeforePermanentDelete : 
ContentType                        : application/octet-stream
LastModified                       : 8/15/2020 7:18:51 PM +00:00
SnapshotTime                       : 
ContinuationToken                  : 
Context                            : Microsoft.WindowsAzure.Commands.Storage.AzureStorageContext
Name                               : scripts/FileToBeCopied.txt

VERBOSE: Performing the operation "Replacing resource group ..." on target "complianceapp".
VERBOSE: 2:18:53 PM - Created resource group 'complianceapp' in location 'eastus'
ResourceGroupName : complianceapp
Location          : eastus
ProvisioningState : Succeeded
Tags              : 
ResourceId        : /subscriptions/6ebd2f8c-21d7-4e7c-a99c-2673781552f6/resourceGroups/complianceapp


Template is valid.
 

==============================
 .\SideLoad-CreateUIDefinition.ps1 -ArtifactsStagingDirectory complianceapp 

Enter credentials to log on to the Azure Portal and fill out the UI parameters.
Open the browser Developer Tools and Console and Copy the Parameters json output that appears there.
Paste the parameters into the azuredeploy.json.parameters file.

Validate the template again:

 .\Deploy-AzureResourceGroup.ps1 -ArtifactStagingDirectory complianceapp -ResourceGroupLocation eastus -UploadArtifacts -ValidateOnly 


==============================

Alternate method to validate:
cd template-validation-tests

npm --folder=..\..\complianceapp run all

==============================





