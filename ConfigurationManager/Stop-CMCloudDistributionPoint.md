Stop-CMCloudDistributionPoint
-----------------------------




### Synopsis
Stops the cloud distribution point service.



---


### Description

The Stop-CMCloudDistributionPoint cmdlet stops the cloud distribution point service.



If you use the Stop-CMCloudDistributionPoint cmdlet, Configuration Manager does not delete content from the distribution point and does not prevent the site server from transferring additional content to the distribution point. While the cloud distribution point service is stopped, the cloud distribution point does not distribute content. Use the Start-CMCloudDistributionPoint (Start-CMCloudDistributionPoint.md)cmdlet to restart distribution.



For example, you might want to stop a cloud service when usage reaches a data threshold and then restart it at a later time.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMCloudDistributionPoint](Get-CMCloudDistributionPoint)



* [New-CMCloudDistributionPoint](New-CMCloudDistributionPoint)



* [Remove-CMCloudDistributionPoint](Remove-CMCloudDistributionPoint)



* [Set-CMCloudDistributionPoint](Set-CMCloudDistributionPoint)



* [Start-CMCloudDistributionPoint](Start-CMCloudDistributionPoint)





---


### Examples
#### Example 1: Stop the cloud distribution point service using an ID
```PowerShell
PS XYZ:\> Stop-CMCloudDistributionPoint -Id "16777242"
```
This command stops the cloud distribution point service for the cloud distribution point that has the specified identifier.
#### Example 2: Stop the cloud distribution point service using a name
```PowerShell
PS XYZ:\> Stop-CMCloudDistributionPoint -Name "West01"
```
This command stops the cloud distribution point service for the cloud distribution point named West01.
#### Example 3: Stop the cloud distribution point service using an object
```PowerShell
PS XYZ:\> $DistPnt = Get-CMCloudDistributionPoint -Id "16777242"
PS XYZ:\> Stop-CMCloudDistributionPoint -InputObject $DistPnt
```
The first command uses the Get-CMCloudDistributionPoint cmdlet to get the distribution point with the specified identifier, and then stores it in the $DistPnt variable.


The second command stops the cloud distribution point service for the distribution point stored in $DistPnt.


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

Specifies an array of identifiers for cloud distribution points. You can use a comma separated list.






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[String]`|true    |named   |False        |AzureServiceId|



#### **InputObject**

Specifies a cloud distribution point object. To get a cloud distribution point object, you can use the Get-CMCloudDistributionPoint cmdlet.






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
Stop-CMCloudDistributionPoint [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Stop-CMCloudDistributionPoint [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Stop-CMCloudDistributionPoint [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
