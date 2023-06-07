Remove-CMApplicationGroup
-------------------------




### Synopsis
Remove an application group.



---


### Description

Use this cmdlet to remove an application group from the site.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMApplicationGroup](Get-CMApplicationGroup)



* [New-CMApplicationGroup](New-CMApplicationGroup)



* [Set-CMApplicationGroup](Set-CMApplicationGroup)



* [Get-CMApplicationGroupDeployment](Get-CMApplicationGroupDeployment)



* [New-CMApplicationGroupDeployment](New-CMApplicationGroupDeployment)



* [Remove-CMApplicationGroupDeployment](Remove-CMApplicationGroupDeployment)



* [Set-CMApplicationGroupDeployment](Set-CMApplicationGroupDeployment)



* [Create application groups](Create application groups)





---


### Examples
#### Example 1: Remove an app group by ID
```PowerShell
Remove-CMApplicationGroup -Id '16778064' -Force
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

Specify the ID of the app group to remove. This value is the same as the CI_ID , for example `1025866`.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |named   |False        |CIId<br/>CI_ID|



#### **InputObject**

Specify an app group object to remove. To get this object, use the Get-CMApplicationGroup (Get-CMApplicationGroup.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases         |
|-----------------|--------|--------|--------------|----------------|
|`[IResultObject]`|true    |named   |True (ByValue)|ApplicationGroup|



#### **ModelName**

Specify the application model identifier of the app group to remove. This value is also known as the CI Unique ID . For example, `ScopeId_0D7D8B60-F2F9-484A-B9F3-4A8B68D14D59/ApplicationGroup_047fbf05-55f4-42ab-9581-e63fd0337fed`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Name**

Specify the name of the app group to remove.






|Type      |Required|Position|PipelineInput|Aliases                                      |
|----------|--------|--------|-------------|---------------------------------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName<br/>ApplicationGroupName|



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
Remove-CMApplicationGroup [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <Int32> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMApplicationGroup [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMApplicationGroup [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -ModelName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMApplicationGroup [-Name] <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
