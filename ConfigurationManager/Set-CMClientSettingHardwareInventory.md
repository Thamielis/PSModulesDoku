Set-CMClientSettingHardwareInventory
------------------------------------




### Synopsis
Sets a client setting hardware inventory.



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
#### **AddInventoryReportClass**

{{ Fill AddInventoryReportClass Description }}






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[IResultObject[]]`|false   |named   |False        |



#### **CleanInventoryReportClass**

{{ Fill CleanInventoryReportClass Description }}






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **CollectMifFile**





Valid Values:

* None
* CollectNoIdMifFile
* CollectIdMifFile
* CollectIdMifAndNoIdMifFile






|Type                 |Required|Position|PipelineInput|Aliases        |
|---------------------|--------|--------|-------------|---------------|
|`[MifCollectionType]`|false   |named   |False        |CollectMifFiles|



#### **DefaultSetting**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Enable**








|Type       |Required|Position|PipelineInput|Aliases                |
|-----------|--------|--------|-------------|-----------------------|
|`[Boolean]`|false   |named   |False        |EnableHardwareInventory|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**








|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **InventoryReportId**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **MaxRandomDelayMins**








|Type     |Required|Position|PipelineInput|Aliases                  |
|---------|--------|--------|-------------|-------------------------|
|`[Int32]`|false   |named   |False        |MaximumRandomDelayMinutes|



#### **MaxThirdPartyMifSize**








|Type     |Required|Position|PipelineInput|Aliases                 |
|---------|--------|--------|-------------|------------------------|
|`[Int32]`|false   |named   |False        |MaximumThirdPartyMifSize|



#### **Name**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PassThru**

Returns an object representing the item with which you are working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveInventoryReportClassById**

{{ Fill RemoveInventoryReportClassById Description }}






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **Schedule**








|Type             |Required|Position|PipelineInput|Aliases                                        |
|-----------------|--------|--------|-------------|-----------------------------------------------|
|`[IResultObject]`|false   |named   |False        |InventorySchedule<br/>HardwareInventorySchedule|



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
Set-CMClientSettingHardwareInventory [-AddInventoryReportClass <IResultObject[]>] [-CleanInventoryReportClass] [-CollectMifFile {None | CollectNoIdMifFile | CollectIdMifFile | CollectIdMifAndNoIdMifFile}] -DefaultSetting [-DisableWildcardHandling] [-Enable <Boolean>] [-ForceWildcardHandling] [-InventoryReportId <String>] [-MaxRandomDelayMins <Int32>] [-MaxThirdPartyMifSize <Int32>] [-PassThru] [-RemoveInventoryReportClassById <String[]>] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSettingHardwareInventory [-AddInventoryReportClass <IResultObject[]>] [-CleanInventoryReportClass] [-CollectMifFile {None | CollectNoIdMifFile | CollectIdMifFile | CollectIdMifAndNoIdMifFile}] [-DisableWildcardHandling] [-Enable <Boolean>] [-ForceWildcardHandling] -InputObject <IResultObject> [-InventoryReportId <String>] [-MaxRandomDelayMins <Int32>] [-MaxThirdPartyMifSize <Int32>] [-PassThru] [-RemoveInventoryReportClassById <String[]>] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSettingHardwareInventory [-AddInventoryReportClass <IResultObject[]>] [-CleanInventoryReportClass] [-CollectMifFile {None | CollectNoIdMifFile | CollectIdMifFile | CollectIdMifAndNoIdMifFile}] [-DisableWildcardHandling] [-Enable <Boolean>] [-ForceWildcardHandling] [-InventoryReportId <String>] [-MaxRandomDelayMins <Int32>] [-MaxThirdPartyMifSize <Int32>] -Name <String> [-PassThru] [-RemoveInventoryReportClassById <String[]>] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
