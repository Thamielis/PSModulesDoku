Invoke-CMEndpointProtectionScan
-------------------------------




### Synopsis
Invokes a scan to detect malware on one or more devices in the Configuration Manager hierarchy.



---


### Description

The Invoke-CMEndpointProtectionScan cmdlet invokes a System Center 2016 Endpoint Protection scan that is outside of any scheduled scans. You can specify the device or collection by using its name, ID, or by specifying an object that represents the device or collection.



For more information about how Configuration Manager supports Endpoint Protection, see Endpoint Protection in Configuration Manager (/mem/configmgr/protect/deploy-use/endpoint-protection).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Endpoint Protection in Configuration Manager](Endpoint Protection in Configuration Manager)



* [Get-CMEndpointProtectionPoint](Get-CMEndpointProtectionPoint)





---


### Examples
#### Example 1: Invoke a full Endpoint Protection scan
```PowerShell
PS XYZ:\>Invoke-CMEndpointProtectionScan -DeviceName "CMCEN-DIST02" -ScanType Full
```
This command invokes a full Endpoint Protection scan of the device named CMCEN-DIST02.


---


### Parameters
#### **Device**

Specifies the device that is scanned for malware.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **DeviceCollection**

Specifies an object that represents a device collection whose members are scanned for malware.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **DeviceCollectionId**

Specifies the ID of a device collection whose members are scanned for malware.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DeviceCollectionName**

Specifies the name of a device collection whose members are scanned for malware.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DeviceId**

Specifies the ID of a device that is scanned for malware.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|true    |named   |False        |ResourceID|



#### **DeviceName**

Specifies the name of a device that is scanned for malware.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Name   |



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



#### **ScanType**

Specifies a full or a quick scan. A full scan looks at every location on the device. A quick scan looks at only those locations where malware is most likely to appear. The acceptable values for this parameter are: Full and Quick.



Valid Values:

* Full
* Quick






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[ScanType]`|false   |named   |False        |



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
Invoke-CMEndpointProtectionScan -Device <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] [-ScanType {Full | Quick}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMEndpointProtectionScan -DeviceCollection <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] [-ScanType {Full | Quick}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMEndpointProtectionScan -DeviceCollectionId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-ScanType {Full | Quick}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMEndpointProtectionScan -DeviceCollectionName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-ScanType {Full | Quick}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMEndpointProtectionScan -DeviceId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-ScanType {Full | Quick}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMEndpointProtectionScan -DeviceName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-ScanType {Full | Quick}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
