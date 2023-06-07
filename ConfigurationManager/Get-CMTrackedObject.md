Get-CMTrackedObject
-------------------




### Synopsis
Gets a tracked object.



---


### Description

> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1
```PowerShell
PS XYZ:\>
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



#### **InputObject**








|Type           |Required|Position|PipelineInput |
|---------------|--------|--------|--------------|
|`[IDisposable]`|false   |named   |True (ByValue)|





---


### Inputs
System.IDisposable





---


### Outputs
* Microsoft.ConfigurationManagement.PowerShell.Provider.ResourceTracker






---


### Notes




---


### Syntax
```PowerShell
Get-CMTrackedObject [-DisableWildcardHandling] [-ForceWildcardHandling] [-InputObject <IDisposable>] [<CommonParameters>]
```
