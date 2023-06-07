New-CMMigrationJob
------------------




### Synopsis
Creates a migration job in Configuration Manager.



---


### Description

The New-CMMigrationJob cmdlet creates a migration job in Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMInitialModifiableSecuredCategory](Get-CMInitialModifiableSecuredCategory)



* [Get-CMMigrationEntity](Get-CMMigrationEntity)



* [Get-CMSecurityScope](Get-CMSecurityScope)





---


### Examples
#### Example 1: Create a migration job
```PowerShell
PS XYZ:\> $CategoryObjects = Get-CMInitialModifiableSecuredCategory
PS XYZ:\> $MigrationEntity = Get-CMMigrationEntity
PS XYZ:\> New-CMMigrationJob -Name "123" -ObjectMigrationJobType -SecurityScope $CategoryObjects -MigrationObject $MigrationEntity
```
The first command uses the Get-CMInitialModifiableSecuredCategory cmdlet and stores the result in the $CategoryObjects variable.


The second command uses the Get-CMMigrationEntity cmdlet and stores the result in the $MigrationEntity variable.


The last command creates a migration job.


---


### Parameters
#### **CollectionLimitingMapping**

Specifies key-value pairings to limit a collection. Collection limiting prevents the addition of collection members you do want in the collection.






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[Hashtable]`|false   |named   |False        |



#### **CollectionMigrationJobType**

Indicates that the job migrates collections, objects, or previously migrated objects.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **ContentObjectsSiteCodeMapping**

Specifies key-value pairs that map content objects in the new site.






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[Hashtable]`|false   |named   |False        |



#### **Description**

Specifies a description for the migration job.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableProgramAfterAdvertisementMigrated**

Indicates whether to enable programs associated with an advertisement after they have migrated.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **MigrateObjectWithSpecifiedCollection**

Indicates that you migrate associated objects with the collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **MigrationCollection**

Specifies an array of input objects.






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[IResultObject[]]`|true    |named   |False        |



#### **MigrationJobSchedule**

Specifies a date time, in D.HH:MM:SS format, to schedule the migration job.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **MigrationObject**

Specifies an array of input objects.






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[IResultObject[]]`|true    |named   |False        |



#### **Name**

Specifies the name of a migration job in Configuration Manager.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ObjectMigrationJobType**

Indicates that the job type is an object migration job.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **ObjectModifiedAfterMigrationJobType**

Indicates that the new migration job only includes objects that were modified since the last migration.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **OverwriteAllObject**

Indicates whether to overwrite objects in the destination database.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SaveCollectionInfoPath**

Specifies a path for the collection information.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SaveObjectInfoPath**

Specifies a path for the object information.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SecurityScope**

Specifies an array of security scope objects. To obtain a security scope object, use the Get-CMSecurityScope (Get-CMSecurityScope.md)cmdlet. The cmdlet applies the security scopes that you specify to data migrated to the destination hierarchy.






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[IResultObject[]]`|true    |named   |False        |



#### **SiteCodeReplacementMapping**

Specifies key-value pairs that map a migrated collection to a site in the destination.






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[Hashtable]`|false   |named   |False        |



#### **TransferOrganizationalFolderStructure**

Indicates whether to migrate an empty collection. Configuration Manager converts the empty collection to an organizational folder.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UtcTime**

Indicates whether to use UTC time.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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
* IResultObject#SMS_MigrationJob






---


### Notes




---


### Syntax
```PowerShell
New-CMMigrationJob [-CollectionLimitingMapping <Hashtable>] -CollectionMigrationJobType [-Description <String>] [-DisableWildcardHandling] [-EnableProgramAfterAdvertisementMigrated <Boolean>] [-ForceWildcardHandling] -MigrationCollection <IResultObject[]> [-MigrationJobSchedule <DateTime>] -Name <String> [-OverwriteAllObject <Boolean>] [-SaveCollectionInfoPath <String>] [-SaveObjectInfoPath <String>] -SecurityScope <IResultObject[]> [-SiteCodeReplacementMapping <Hashtable>] [-TransferOrganizationalFolderStructure <Boolean>] [-UtcTime <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMMigrationJob [-CollectionLimitingMapping <Hashtable>] -CollectionMigrationJobType [-ContentObjectsSiteCodeMapping <Hashtable>] [-Description <String>] [-DisableWildcardHandling] [-EnableProgramAfterAdvertisementMigrated <Boolean>] [-ForceWildcardHandling] -MigrateObjectWithSpecifiedCollection -MigrationCollection <IResultObject[]> [-MigrationJobSchedule <DateTime>] -MigrationObject <IResultObject[]> -Name <String> [-OverwriteAllObject <Boolean>] [-SaveCollectionInfoPath <String>] [-SaveObjectInfoPath <String>] -SecurityScope <IResultObject[]> [-SiteCodeReplacementMapping <Hashtable>] [-TransferOrganizationalFolderStructure <Boolean>] [-UtcTime <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMMigrationJob [-ContentObjectsSiteCodeMapping <Hashtable>] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-MigrationJobSchedule <DateTime>] -MigrationObject <IResultObject[]> -Name <String> -ObjectMigrationJobType [-OverwriteAllObject <Boolean>] [-SaveObjectInfoPath <String>] -SecurityScope <IResultObject[]> [-SiteCodeReplacementMapping <Hashtable>] [-TransferOrganizationalFolderStructure <Boolean>] [-UtcTime <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMMigrationJob [-ContentObjectsSiteCodeMapping <Hashtable>] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-MigrationJobSchedule <DateTime>] -MigrationObject <IResultObject[]> -Name <String> -ObjectModifiedAfterMigrationJobType [-OverwriteAllObject <Boolean>] [-SaveObjectInfoPath <String>] -SecurityScope <IResultObject[]> [-SiteCodeReplacementMapping <Hashtable>] [-TransferOrganizationalFolderStructure <Boolean>] [-UtcTime <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
