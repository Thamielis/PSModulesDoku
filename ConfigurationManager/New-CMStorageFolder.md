New-CMStorageFolder
-------------------




### Synopsis
Creates a new storage folder in Configuration Manager.



---


### Description

The New-CMStoragefolder cmdlet creates a new storage folder to store user migration data in Configuration Manager.



A storage folder identifies a location on a state migration point site system to store user migration data. Use this cmdlet in conjunction with the Add-CMStateMigrationPoint (Add-CMStateMigrationPoint.md)cmdlet to create a new state migration point with storage folders.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1: Create a new storage folder
```PowerShell
PS XYZ:\> New-CMStoragefolder -MaximumClientNumber 80 -MinimumFreeSpace 10 -SpaceUnit Megabyte -StorageFolderName "D:\Contoso-Mobile-Users"
```
This command creates a new storage folder for migration data by using the maximum number of clients, minimum free space, and storage folder path parameters.


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



#### **MaximumClientNumber**

Specifies the maximum number of clients that the storage folder can hold. The storage folder contains user state migration data in Configuration Manager. Valid values are: numbers between 1 and 99999.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **MinimumFreeSpace**

Specifies the minimum amount of free space for storage of user state migration data. Valid values are: numbers between 1 - 99999 when specifying a byte value, or numbers between 1 - 100 when specifying a percentage.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **SpaceUnit**

Specifies the storage units for the MinimumFreeSpace parameter.



Valid Values:

* Megabyte
* Gigabyte
* Percent






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[MinSpaceType]`|false   |named   |False        |



#### **StorageFolderName**

Specifies a local path for the storage folder. The associated state migration point site system role in Configuration Manager uses this path.






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
None





---


### Outputs
* Microsoft.ConfigurationManagement.PowerShell.Cmdlets.HS.StorageDirectoryData






---


### Notes




---


### Syntax
```PowerShell
New-CMStorageFolder [-DisableWildcardHandling] [-ForceWildcardHandling] [-MaximumClientNumber <Int32>] [-MinimumFreeSpace <Int32>] [-SpaceUnit {Megabyte | Gigabyte | Percent}] -StorageFolderName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
