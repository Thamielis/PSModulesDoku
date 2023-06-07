Remove-CMCloudManagementGateway
-------------------------------




### Synopsis
Remove a cloud management gateway.



---


### Description

Use this cmdlet to remove a cloud management gateway (CMG) service from the site.



For more information, see CMG Overview (/mem/configmgr/core/clients/manage/cmg/overview).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMCloudManagementGateway](Get-CMCloudManagementGateway)



* [New-CMCloudManagementGateway](New-CMCloudManagementGateway)



* [Set-CMCloudManagementGateway](Set-CMCloudManagementGateway)



* [Start-CMCloudManagementGateway](Start-CMCloudManagementGateway)



* [Stop-CMCloudManagementGateway](Stop-CMCloudManagementGateway)





---


### Examples
#### Example 1
```PowerShell
Get-CMCloudManagementGateway -Name "GraniteFalls.cloudapp.net" | Remove-CMCloudManagementGateway
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Run the command without asking for confirmation.






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






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[String]`|true    |named   |False        |AzureServiceId|



#### **InputObject**

Specify a CMG object to remove. To get this object, use the Get-CMCloudManagementGateway (Get-CMCloudManagementGateway.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specify the service name for the CMG in Azure.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Confirm**
-Confirm is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-Confirm is used to -Confirm each operation.

If you pass ```-Confirm:$false``` you will not be prompted.


If the command sets a ```[ConfirmImpact("Medium")]``` which is lower than ```$confirmImpactPreference```, you will not be prompted unless -Confirm is passed.

#### **WhatIf**
-WhatIf is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-WhatIf is used to see what would happen, or return operations without executing them


---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Remove-CMCloudManagementGateway [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCloudManagementGateway [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCloudManagementGateway [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
