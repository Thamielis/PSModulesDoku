Get-CMAzureService
------------------




### Synopsis
Get an Azure service.



---


### Description

Use this cmdlet to get the Azure service. For more information, see Configure Azure services (/mem/configmgr/core/servers/deploy/configure/azure-services-wizard).



> [!NOTE] > This cmdlet might work with other Azure services, but it's only tested with the Cloud management connection to support the cloud management gateway (CMG).



---


### Related Links
* [Remove-CMAzureService](Remove-CMAzureService)



* [Configure Azure services](Configure Azure services)





---


### Examples
#### Example 1: Get the Azure service by name
```PowerShell
Get-CMAzureService -Name "Contoso"
```

#### Example 2: Get the Azure service by ID
```PowerShell
Get-CMAzureService -Id 2
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the site's ID for the Azure service. The Id is the integer value stored in the site database for the service. For example, run the following SQL query, and look at the ID column: `select * from Azure_CloudService`.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |named   |False        |AzureServiceId|



#### **Name**

Specify the site's name for the Azure service. The Name is the same value as in the Azure Services node in the console.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject#SMS_Azure_CloudService






---


### Notes




---


### Syntax
```PowerShell
Get-CMAzureService [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <Int32> [<CommonParameters>]
```
```PowerShell
Get-CMAzureService [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
