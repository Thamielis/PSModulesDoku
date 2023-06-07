Unlock-CMObject
---------------




### Synopsis
Release a SEDO lock on an object.



---


### Description

> [!WARNING] > Configuration Manager cmdlets automatically lock and unlock objects. Use of this cmdlet may interfere with the functionality of other cmdlets.



The Unlock-CMObject cmdlet releases the SEDO lock on one or more objects. Configuration Manager SEDO (Serialized Editing of Distributed Objects) is a mechanism to assign locks to globally replicated objects. If a user wants to edit and save an object, they have to get a lock from the site. The site assigns a lock to the user for that object, on their computer, and in the site. While the user has the lock, no one else can edit the object.



For more information, see Configuration Manager SEDO (/mem/configmgr/develop/core/understand/sedo).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Lock-CMObject](Lock-CMObject)



* [Get-CMObjectLockDetails](Get-CMObjectLockDetails)



* [Configuration Manager SEDO](Configuration Manager SEDO)





---


### Examples
#### Example 1: Unlock a driver package
```PowerShell
$CIObj = Get-CMDriverPackage -Id "CM100042"
Unlock-CMObject $CIObj
Get-CMObjectLockDetails -InputObject $CIObj
```



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

Specify an array of Configuration Manager objects that are output from another cmdlet. For example, to get an application object, use the Get-CMApplication (Get-CMApplication.md)cmdlet.


For a list of objects that are SEDO-enabled, see Configuration Manager SEDO (/mem/configmgr/develop/core/understand/sedo).






|Type               |Required|Position|PipelineInput |
|-------------------|--------|--------|--------------|
|`[IResultObject[]]`|true    |0       |True (ByValue)|



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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject[]





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Unlock-CMObject [-InputObject] <IResultObject[]> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
