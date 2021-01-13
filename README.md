# azchlg
azure challenge

Create a resource group by using name , location and tags through powershell or azure portal

Powershell commands:
Account-connect:
Connect-AzAccount
Resource group creation:
New-AzResourceGroup -ResourceGroupName "sample" -Location "east us" -tag @{'resources'='loadbalancers'}
Get-AzResourceGroup -ResourceGroupName sample
 

Deploy arm template with locally stored json files:

New-AzResourceGroupDeployment -Name test -ResourceGroupName sample -TemplateParameterFile "D:\azchlg\loadbalancer\azuredeploy.parameters.json" -TemplateFile "D:\azchlg\loadbalancer\azuredeploy.json"
 

Deploy arm template using uri:

New-AzResourceGroupDeployment -Name test -ResourceGroupName sample -TemplateUri 'https://raw.githubusercontent.com/kamalanathan1995/azchlg/master/loadbalancer/azuredeploy.json' -TemplateParameterUri 'https://raw.githubusercontent.com/kamalanathan1995/azchlg/master/loadbalancer/azuredeploy.parameters.json'
 















I have included command to install the web server on VM’s to test the load balancer connections:

# install IIS server role
 Install-WindowsFeature -name Web-Server -IncludeManagementTools

 # remove default htm file
  remove-item  C:\inetpub\wwwroot\iisstart.htm

 # Add a new htm file that displays server name
  Add-Content -Path "C:\inetpub\wwwroot\iisstart.htm" -Value $("Hello World from " + $env:computername)


Test success output:
 

 
