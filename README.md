# cloudSwXtch-templates
Templates to create a cloudSwXtch from the marketplace. The cloudSwXtch is deployed as a VM image so can be created with any tools that create VMs. However, to function properly the cloudSwXtch **needs two network interfaces** and the second interface needs to have Accelerated Networking enabled. Use these templates to simplify deploying a cloudSwXtch since these templates ensure correct setup of the network interfaces.

## Install template into the Azure Protal

This proceedure will install the template into a resource group in your Azure subscription. You only have to do this once and then you can use the template in the Portal to provide a simple UI to cretae cloudSwXtches.

1. Log into the Azure Portal
2. Pick a resource group to hold the template. You can use an existing group or create a new one.
3. Launch the Azure cloud shell (https://learn.microsoft.com/en-us/azure/cloud-shell/overview)
4. Run the following commands. Replace <your-rg-here> with the name of the resouce group from step #2.


```
rg="<your-rg-here>"
git clone https://github.com/swxtchio/cloudSwXtch-AzureTemplates
cd cloudSwXtch-AzureTemplates
az ts create -n cloudSwxtch-from-mp-image -g $rg -v 1 -f TemplateVM.json --ui-form-definition TemplateUI.json
```

## Using the template

Using the template once it has been installed to your subscription is easy. Within the Azure Portal navagate to the template and choose **Deploy**.
  
1. Log into the Azure Portal
2. Navagate to the template
   - Find the resource group holding the template then select the template
   - Or, use the "Search resource, services, and docs" bar (G+/) and enter "cloudSwxtch-from-mp-image" in the search. This will take to directly to the template. Select the template.
3. Click "Deploy" to launch the template UI
  
