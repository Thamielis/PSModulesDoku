Set-CMStateMigrationPoint
-------------------------




### Synopsis
Modifies settings for a state migration point in Configuration Manager.



---


### Description

The Set-CMStateMigrationPoint cmdlet modifies settings for a state migration point in Configuration Manager. A state migration point is a site system role that manages data transfer from client computers during an operating system installation process. Use this cmdlet to modify the boundary groups and storage folders associated with the migration point, how long to wait before the migration point deletes client data, whether to allow a fallback source location for content, and whether to enable restore only mode.



You can specify which migration point to modify by using the site system server name and the site code, or use the Get-CMStateMigrationPoint (Get-CMStateMigrationPoint.md)cmdlet.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMStateMigrationPoint](Add-CMStateMigrationPoint)



* [Get-CMStateMigrationPoint](Get-CMStateMigrationPoint)



* [Remove-CMStateMigrationPoint](Remove-CMStateMigrationPoint)



* [New-CMStoragefolder](New-CMStoragefolder)





---


### Examples
#### Example 1: Modify a state migration point
```PowerShell
PS XYZ:\> $StateMigrationPoint = Get-CMStateMigrationPoint -SiteCode "CM4" -SiteSystemServerName "MigrationServer.TSQA.Contoso.com"
PS XYZ:\> Set-CMStateMigrationPoint -InputObject $StateMigrationPoint -AllowFallbackSourceLocationForContent $True -TimeDeleteAfter 12 -TimeUnit Hours
```
This example modifies a migration point named MigrationServer.TSQA.Contoso.com for the site that has the code CM4. The example changes the migration point to allow a fallback source location for content, and modifies how long after data download to delete data.


The first command uses the Get-CMStateMigrationPoint cmdlet to obtain a migration point for the specified site code and server name, and stores it in the $StateMigrationPoint variable.


The second command modifies the input object stored in the $StateMigrationPoint variable. The command sets the AllowFallbackSourceLocationForContent parameter to $True, and modifies the time to delete after to 12 hours.
#### Example 2: Modify storage folders and boundary groups for a state migration point
```PowerShell
PS XYZ:\> $Storage01 = New-CMStoragefolder -MaximumClientNumber 100 -MinimumFreeSpace 100 -SpaceUnit Megabyte -StorageFolderName "C:\"
PS XYZ:\> $Storage02 = New-CMStoragefolder -MaximumClientNumber 100 -MinimumFreeSpace 10 -SpaceUnit Gigabyte -StorageFolderName "D:\"
PS XYZ:\> Set-CMStateMigrationPoint -SiteCode "CM4" -SiteSystemServerName "MigrationServer.TSQA.Contoso.com" -AddBoundaryGroupName "BG07" -AddStorageFolder $Storage02 -AllowFallbackSourceLocationForContent $False -DeleteImmediately -EnableRestoreOnlyMode $True -RemoveBoundaryGroupName "BG22" -RemoveStorageFolder $Storage01
```
This example modifies settings for a state migration point named MigrationServer.TSQA.Contoso.com for the site that has the site code CM4. The example substitutes a different boundary group and different storage folder, and modifies other settings.


The first command uses the New-CMStoragefolder cmdlet to create a storage folder object, and stores it in the $Storage01 variable. Consult documentation for that cmdlet for more information.


The second command uses the New-CMStoragefolder cmdlet to create a storage folder object, and stores it in the $Storage02 variable.


The third command removes the storage folder stored in the $Storage01 variable from the migration point and, in the same command, adds the storage folder stored in the $Storage02 variable to the migration point. Likewise, the command removes the boundary group named BG22 and adds the boundary group named BG07. The command also specifies a value of $False for the AllowFallbackSourceLocationForContent parameter and a value of $True for the EnableRestoreOnlyMode parameter. The command uses the DeleteImmediately parameter; therefore, the migration point deletes client information immediately after download.


---


### Parameters
#### **AddBoundaryGroupName**

Specifies an array of boundary group names. The cmdlet adds these boundary groups to the state migration point. During migration, clients in a boundary group use this site as a source location for content.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **AddStorageFolder**

Specifies an array of storage folders, as storage directory data objects. The cmdlet adds these folders to the state migration point. To obtain a storage directory data object, use the New-CMStoragefolder (New-CMStoragefolder.md)cmdlet.


A state migration point stores user state data when it migrates a computer to a new operating system.






|Type                      |Required|Position|PipelineInput|
|--------------------------|--------|--------|-------------|
|`[StorageDirectoryData[]]`|false   |named   |False        |



#### **AllowFallbackSourceLocationForContent**

Indicates whether a fallback source location is available.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **DeleteImmediately**

Indicates that deletion of client data occurs immediately after the target computer downloads that data. If you select a value of $False, specify how long to wait by using the TimeDeleteAfter and TimeUnit parameters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableRestoreOnlyMode**

Indicates whether to enable restore only mode. In restore only mode, Configuration Manager refuses new requests to store client data.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specifies a state migration point object. To obtain a state migration point object, use the Get-CMStateMigrationPoint (Get-CMStateMigrationPoint.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases            |
|-----------------|--------|--------|--------------|-------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|StateMigrationPoint|



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveBoundaryGroupName**

Specifies an array of boundary group names. The cmdlet removes these boundary groups from the state migration point. During migration, clients in a boundary group use this site as a source location for content.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **RemoveStorageFolder**

Specifies an array of storage folders, as storage directory data objects. The cmdlet removes these folders from the state migration point. A state migration point stores user state data when it migrates a computer to a new operating system.






|Type                      |Required|Position|PipelineInput|
|--------------------------|--------|--------|-------------|
|`[StorageDirectoryData[]]`|false   |named   |False        |



#### **SiteCode**

Specifies the site code for a Configuration Manager site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies the host name for a state migration point.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|true    |0       |False        |Name<br/>ServerName|



#### **TimeDeleteAfter**

Specifies the amount of time to wait after the target computer downloads data to delete that data. Specify a time unit by using the TimeUnit parameter. To delete data immediately, specify a value of $True for the DeleteImmediately parameter.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **TimeUnit**

Specifies a time unit for the value specified in the TimeDeleteAfter parameter. The acceptable values for this parameter are: Days and Hours.



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
Set-CMStateMigrationPoint [-AddBoundaryGroupName <String[]>] [-AddStorageFolder <StorageDirectoryData[]>] [-AllowFallbackSourceLocationForContent <Boolean>] [-DeleteImmediately] [-DisableWildcardHandling] [-EnableRestoreOnlyMode <Boolean>] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] [-RemoveBoundaryGroupName <String[]>] [-RemoveStorageFolder <StorageDirectoryData[]>] [-TimeDeleteAfter <Int32>] [-TimeUnit {Hours | Days}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMStateMigrationPoint [-SiteSystemServerName] <String> [-AddBoundaryGroupName <String[]>] [-AddStorageFolder <StorageDirectoryData[]>] [-AllowFallbackSourceLocationForContent <Boolean>] [-DeleteImmediately] [-DisableWildcardHandling] [-EnableRestoreOnlyMode <Boolean>] [-ForceWildcardHandling] [-PassThru] [-RemoveBoundaryGroupName <String[]>] [-RemoveStorageFolder <StorageDirectoryData[]>] [-SiteCode <String>] [-TimeDeleteAfter <Int32>] [-TimeUnit {Hours | Days}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
