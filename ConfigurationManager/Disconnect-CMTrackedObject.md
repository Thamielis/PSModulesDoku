Disconnect-CMTrackedObject
--------------------------




### Synopsis
Clean up unused PowerShell objects to avoid SMS Provider quota violation errors.



---


### Description

When you use Start-CMObjectTracking to track SMS Provider objects used by the PowerShell runtime, use this cmdlet to clean up these resources when they're no longer needed.



When you run Start-CMObjectTracking , the PowerShell runtime tracks IResultObject objects created by Configuration Manager cmdlets. For objects that aren't manually cleaned up with `.Dispose()`, reclaim them by using Disconnect-CMTrackedObject against an individual object.



Once an object is reclaimed, it can no longer be reused or passed to another cmdlet through the object pipeline. Stop-CMObjectTracking can be used to turn off object tracking. Previously allocated objects remain active.



Unclaimed resources can cause the SMS Provider to raise quota violation errors. These quota issues typically manifest from working with large sets of SMS Provider objects or in long-running environments.



> [!NOTE] > This feature is experimental and may be subject to change or removal in a future release. > > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Start-CMObjectTracking](Start-CMObjectTracking)



* [Stop-CMObjectTracking](Stop-CMObjectTracking)





---


### Examples
#### Example 1
```PowerShell
Start-CMObjectTracking

# Reclaim a single tracked object
$obj | Disconnect-CMTrackedObject -Force

# Reclaim all tracked objects
Disconnect-CMTrackedObject -All

Stop-CMObjectTracking
```



---


### Parameters
#### **All**

Add this parameter to reclaim all tracked objects.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Add this parameter to run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify any IResultObject that you previously created with a Configuration Manager cmdlet.






|Type             |Required|Position|PipelineInput |Aliases     |
|-----------------|--------|--------|--------------|------------|
|`[IDisposable[]]`|true    |named   |True (ByValue)|InputObjects|



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
System.IDisposable[]





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Disconnect-CMTrackedObject -All [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Disconnect-CMTrackedObject [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IDisposable[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
