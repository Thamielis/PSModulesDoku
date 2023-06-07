Add-CMStateMigrationPoint
-------------------------




### Synopsis
Adds a state migration point in Configuration Manager.



---


### Description

The Add-CMStateMigrationPoint cmdlet adds a state migration point in Configuration Manager. A state migration point is a site system role that manages data transfer from client computers during an operating system installation process.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMStateMigrationPoint](Get-CMStateMigrationPoint)



* [Remove-CMStateMigrationPoint](Remove-CMStateMigrationPoint)



* [Set-CMStateMigrationPoint](Set-CMStateMigrationPoint)



* [Get-CMBoundaryGroup](Get-CMBoundaryGroup)





---


### Examples
#### Example 1: Add a state migration point
```PowerShell
PS XYZ:\> $s1 = New-CMStoragefolder -StorageFolderName "C:\Sto-1" -MaximumClientNumber 100 -MinimumFreeSpace 100 -SpaceUnit Megabyte
PS XYZ:\> $s2 = New-CMStoragefolder -StorageFolderName "D:\Sto-2" -MaximumClientNumber 100 -MinimumFreeSpace 10 -SpaceUnit Gigabyte
PS XYZ:\> Add-CMStateMigrationPoint -SiteSystemServerName "Contoso-Migration.Contoso.com" -SiteCode "CM2" -StorageFolders $s1,$s2 -DeleteImmediately -EnableRestoreOnlyMode $False -AllowFallbackSourceLocationForContent $False -BoundaryGroupName "CMC"
```
The first command creates a storage folder on the C: drive that has a maximum number of clients setting and a minimum free space setting. The command stores the result in the $s1 variable.


The second command creates a storage folder on the D: drive that has a maximum number of clients setting and a minimum free space setting. The command stores the result in the $s2 variable.


The third command adds a state migration point.


---


### Parameters
#### **AllowFallbackSourceLocationForContent**

Indicates whether a fallback source location is available.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **BoundaryGroupName**

Specifies an array of names of boundary groups. You can get a boundary group name by using the Get-CMBoundaryGroup (Get-CMBoundaryGroup.md)cmdlet.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **DeleteImmediately**

Indicates that Configuration Manager deletes client data immediately after the target computer downloads the data.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableRestoreOnlyMode**

Indicates whether to enable restore only mode. If this mode is enabled, Configuration Manager refuses new requests to store client data.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specifies the input to this cmdlet. You can use this parameter, or you can pipe the input to this cmdlet.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|SiteServer|



#### **SiteCode**

Specifies the Configuration Manager site that hosts this site system role.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies the name of the site system server in Configuration Manager.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|true    |0       |False        |Name<br/>ServerName|



#### **StorageFolder**








|Type                      |Required|Position|PipelineInput|Aliases       |
|--------------------------|--------|--------|-------------|--------------|
|`[StorageDirectoryData[]]`|true    |named   |False        |StorageFolders|



#### **TimeDeleteAfter**

Specifies a time interval to wait before client data is deleted.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **TimeUnit**

Specifies the unit of time for the TimeDeleteAfter parameter. Valid values are: Days and Hours.



Valid Values:

* Hours
* Days






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[IntervalType]`|false   |named   |False        |



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
* IResultObject#SMS_SCI_SysResUse






---


### Notes




---


### Syntax
```PowerShell
Add-CMStateMigrationPoint [-AllowFallbackSourceLocationForContent <Boolean>] [-BoundaryGroupName <String[]>] [-DeleteImmediately] [-DisableWildcardHandling] [-EnableRestoreOnlyMode <Boolean>] [-ForceWildcardHandling] -InputObject <IResultObject> -StorageFolder <StorageDirectoryData[]> [-TimeDeleteAfter <Int32>] [-TimeUnit {Hours | Days}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMStateMigrationPoint [-SiteSystemServerName] <String> [-AllowFallbackSourceLocationForContent <Boolean>] [-BoundaryGroupName <String[]>] [-DeleteImmediately] [-DisableWildcardHandling] [-EnableRestoreOnlyMode <Boolean>] [-ForceWildcardHandling] [-SiteCode <String>] -StorageFolder <StorageDirectoryData[]> [-TimeDeleteAfter <Int32>] [-TimeUnit {Hours | Days}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
