Move-CMObject
-------------




### Synopsis
Move a Configuration Manager object into a different folder.



---


### Description

The Move-CMObject cmdlet moves a Configuration Manager object into a different folder. Specify the object to move and the destination folder. Because an object exists in only one folder, the cmdlet doesn't specify the current folder.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Lock-CMObject](Lock-CMObject)



* [Unlock-CMObject](Unlock-CMObject)





---


### Examples
#### Example 1: Move an app by object
```PowerShell
$app = Get-CMApplication -Name "Teams"
Move-CMObject -FolderPath "XYZ:\Application\TestFolder" -InputObject $app
```

#### Example 2: Move a task sequence by ID
```PowerShell
Move-CMObject -FolderPath "XYZ:\TaskSequence\Development" -ObjectId "XYZ00550"
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FolderPath**

Specifies a destination folder path, in the following format: `<site code>:<object type>\folder\subfolder\subfolder`.


* `<site code>`: The Configuration Manager site code.


* `<object type>`: One of the following keywords for the type of object to move:


* Application - BootImage - ConfigurationBaseline - ConfigurationItem - DeviceCollection - Driver - DriverPackage - OperatingSystemImage - OperatingSystemInstaller - Package - Query - TaskSequence - UserCollection - UserStateMigration For example, a folder named LOB Apps for an application at the site CM1 has the following file path: `CM1:\Application\LOB Apps`.


To move an object to the root folder, don't specify a folder. For example, `CM1:\Application`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify an array of Configuration Manager objects to move. If you specify an array, use the same object type. Match the object type with the keyword used with the -FolderPath parameter.


Use one of the following cmdlets to get these objects:


* Get-CMApplication (Get-CMApplication.md)- Get-CMPackage (Get-CMPackage.md)- Get-CMDriverPackage (Get-CMDriverPackage.md)- Get-CMOperatingSystemImage (Get-CMOperatingSystemImage.md)- Get-CMOperatingSystemInstaller (Get-CMOperatingSystemInstaller.md)- Get-CMBootImage (Get-CMBootImage.md)- Get-CMTaskSequence (Get-CMTaskSequence.md)






|Type               |Required|Position|PipelineInput |
|-------------------|--------|--------|--------------|
|`[IResultObject[]]`|true    |named   |True (ByValue)|



#### **ObjectId**

Specifies an array of object IDs to move. If you specify an array, use the same object type. Match the object type with the keyword used with the -FolderPath parameter.


For example, `XYZ00550`.






|Type        |Required|Position|PipelineInput|Aliases    |
|------------|--------|--------|-------------|-----------|
|`[String[]]`|true    |named   |False        |InstanceKey|



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
Move-CMObject [-DisableWildcardHandling] -FolderPath <String> [-ForceWildcardHandling] -InputObject <IResultObject[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Move-CMObject [-DisableWildcardHandling] -FolderPath <String> [-ForceWildcardHandling] -ObjectId <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
