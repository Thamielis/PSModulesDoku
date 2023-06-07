Remove-CMCloudDistributionPoint
-------------------------------




### Synopsis
Removes cloud-based distribution points.



---


### Description

The Remove-CMCloudDistributionPoint cmdlet removes specified cloud-based distribution points.



When you remove a distribution point, Configuration Manager deletes all the content stored there. If you want to suspend a distribution point temporarily, use the Stop-CMCloudDistributionPoint (Stop-CMCloudDistributionPoint.md)cmdlet.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMCloudDistributionPoint](Get-CMCloudDistributionPoint)



* [New-CMCloudDistributionPoint](New-CMCloudDistributionPoint)



* [Set-CMCloudDistributionPoint](Set-CMCloudDistributionPoint)



* [Start-CMCloudDistributionPoint](Start-CMCloudDistributionPoint)



* [Stop-CMCloudDistributionPoint](Stop-CMCloudDistributionPoint)





---


### Examples
#### Example 1: Remove all distribution points
```PowerShell
PS XYZ:\> Remove-CMCloudDistributionPoint
```
This command removes all the cloud distribution points from Configuration Manager. Unless you use the Force parameter, the cmdlet prompts you for confirmation.
#### Example 2: Remove a distribution point using a name
```PowerShell
PS XYZ:\> Remove-CMCloudDistributionPoint -Name "West01"
```
This command removes the cloud distribution point named West01. Unless you use the Force parameter, the cmdlet prompts you for confirmation.
#### Example 3: Remove a distribution point using an ID
```PowerShell
PS XYZ:\> Remove-CMCloudDistributionPoint -Id "16777236"
```
This command removes the cloud distribution point that has the specified identifier. Unless you use the Force parameter, the cmdlet prompts you for confirmation.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Forces the command to run without asking for user confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specifies an array of identifiers for cloud distribution points. You can use a comma separated list.






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[String]`|true    |named   |False        |AzureServiceId|



#### **InputObject**

Specifies a cloud distribution point object. To obtain a cloud distribution point object, you can use the Get-CMCloudDistributionPoint cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies the name of a cloud distribution point.






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
Remove-CMCloudDistributionPoint [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCloudDistributionPoint [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCloudDistributionPoint [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
