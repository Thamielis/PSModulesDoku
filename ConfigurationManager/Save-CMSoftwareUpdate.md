Save-CMSoftwareUpdate
---------------------




### Synopsis
Save software updates to update groups and packages.



---


### Description

Use this cmdlet to save one or more software updates to update groups and deployment packages.



You can specify one or more software updates associated with deployment packages. You can also specify the download source location of updates and the language of the software updates. Languages determine which summary details a software update synchronizes and the file languages to be downloaded for software updates.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSoftwareUpdate](Get-CMSoftwareUpdate)



* [Get-CMSoftwareUpdateGroup](Get-CMSoftwareUpdateGroup)



* [Set-CMSoftwareUpdate](Set-CMSoftwareUpdate)



* [Sync-CMSoftwareUpdate](Sync-CMSoftwareUpdate)



* [Remove-CMSoftwareUpdateFromPackage](Remove-CMSoftwareUpdateFromPackage)





---


### Examples
#### Example 1: Save a software update and add a language to it
```PowerShell
Save-CMSoftwareUpdate -SoftwareUpdateName "Cumulative Update for Windows 10 (KB3095020)" -DeploymentPackageName "Package01" -SoftwareUpdateLanguage "English"
```

#### Example 2: Save a software update from a software update group
```PowerShell
Get-CMSoftwareUpdateGroup -Name "TestSUgroup10" | Save-CMSoftwareUpdate -DeploymentPackageName "Package01"
```

#### Example 3: Save a software update from a software update group and specify a source location to download from
```PowerShell
Get-CMSoftwareUpdateGroup -Name "TestSUgroup10" Save-CMSoftwareUpdate -Location "\\Server01\Updates" -DeploymentPackageName "Package01"
```



---


### Parameters
#### **DeploymentPackageName**

Specify the name of a deployment package.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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



#### **Location**

Specify a download source location for software updates.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **RetryCount**

Specify an integer value for the number of times to retry downloading the update.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[UInt32]`|false   |named   |False        |



#### **RetryDelaySec**

Specify an integer value for the number of seconds to wait before retrying.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[UInt32]`|false   |named   |False        |



#### **SoftwareUpdate**

Specify a software update object to save. To get this object, use the Get-CMSoftwareUpdate (Get-CMSoftwareUpdate.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **SoftwareUpdateGroup**

Specify a software update group object. To get this object, use the Get-CMSoftwareUpdateGroup (Get-CMSoftwareUpdateGroup.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **SoftwareUpdateGroupId**

Specify an array of IDs of software update groups.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|true    |named   |False        |



#### **SoftwareUpdateGroupName**

Specify an array of names of software update groups.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|true    |named   |False        |



#### **SoftwareUpdateId**

Specify an array of IDs of software updates.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|true    |named   |False        |



#### **SoftwareUpdateLanguage**

Specify an array of software update languages.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **SoftwareUpdateName**

Specify an array of software update names.






|Type        |Required|Position|PipelineInput|Aliases             |
|------------|--------|--------|-------------|--------------------|
|`[String[]]`|true    |named   |False        |LocalizedDisplayName|



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
Save-CMSoftwareUpdate -DeploymentPackageName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Location <String>] [-RetryCount <UInt32>] [-RetryDelaySec <UInt32>] -SoftwareUpdate <IResultObject> [-SoftwareUpdateLanguage <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Save-CMSoftwareUpdate -DeploymentPackageName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Location <String>] [-RetryCount <UInt32>] [-RetryDelaySec <UInt32>] -SoftwareUpdateGroup <IResultObject> [-SoftwareUpdateLanguage <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Save-CMSoftwareUpdate -DeploymentPackageName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Location <String>] [-RetryCount <UInt32>] [-RetryDelaySec <UInt32>] -SoftwareUpdateGroupId <String[]> [-SoftwareUpdateLanguage <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Save-CMSoftwareUpdate -DeploymentPackageName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Location <String>] [-RetryCount <UInt32>] [-RetryDelaySec <UInt32>] -SoftwareUpdateGroupName <String[]> [-SoftwareUpdateLanguage <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Save-CMSoftwareUpdate -DeploymentPackageName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Location <String>] [-RetryCount <UInt32>] [-RetryDelaySec <UInt32>] -SoftwareUpdateId <String[]> [-SoftwareUpdateLanguage <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Save-CMSoftwareUpdate -DeploymentPackageName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Location <String>] [-RetryCount <UInt32>] [-RetryDelaySec <UInt32>] [-SoftwareUpdateLanguage <String[]>] -SoftwareUpdateName <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
