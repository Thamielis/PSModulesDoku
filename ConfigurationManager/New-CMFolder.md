New-CMFolder
------------




### Synopsis
Create one or more folders in the console.



---


### Description

Use this cmdlet to create a new folder under the specified parent folder path.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMFolder](Get-CMFolder)



* [Remove-CMFolder](Remove-CMFolder)



* [Set-CMFolder](Set-CMFolder)





---


### Examples
#### Example 1
```PowerShell
$parentPath = 'DeviceCollection'
$name =  'Folder1'
$folder = New-CMFolder -ParentFolderPath $parentPath -Name $name
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

Specify a folder object for the parent container. To get this object, use the Get-CMFolder (Get-CMFolder.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases            |
|-----------------|--------|--------|--------------|-------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|ParentContainerNode|



#### **Name**

Specify a name for the folder to create.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ParentFolderPath**

Specify the path of the parent folder.






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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject#SMS_ObjectContainerNode






---


### Notes
For more information on this return object and its properties, see SMS_ObjectContainerNode server WMI class (/mem/configmgr/develop/reference/core/servers/console/sms_objectcontainernode-server-wmi-class).



---


### Syntax
```PowerShell
New-CMFolder [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Name <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMFolder [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] -ParentFolderPath <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
