Remove-CMResource
-----------------




### Synopsis
Removes a Configuration Manager resource.



---


### Description

The Remove-CMResource cmdlet removes a resource.



A resource can be a user or a device.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMResource](Get-CMResource)





---


### Examples
#### Example 1: Remove a resource by using the pipeline
```PowerShell
PS XYZ:\> Get-CMResource -ResourceID 2063597568 -Fast| Remove-CMResource -Force
```
This command gets the resource object with the ID of 2063597568 and uses the pipeline operator to pass the object to Remove-CMResource , which removes the resource without prompting for user confirmation.
#### Example 2: Remove a resource by ID
```PowerShell
PS XYZ:\> Remove-CMResource -ResourceID 2097152000
```
This command removes the resource with the ID of 2097152000.


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



#### **InputObject**

Specifies a resource object. To obtain a resource object, use the Get-CMResource cmdlet.






|Type             |Required|Position|PipelineInput |Aliases |
|-----------------|--------|--------|--------------|--------|
|`[IResultObject]`|true    |0       |True (ByValue)|Resource|



#### **ResourceId**

Specifies the ID of a resource.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|true    |0       |False        |



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
Remove-CMResource [-InputObject] <IResultObject> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMResource [-ResourceId] <Int32> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
