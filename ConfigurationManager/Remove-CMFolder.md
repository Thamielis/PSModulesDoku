Remove-CMFolder
---------------




### Synopsis
Remove the specified folder in the console.



---


### Description

Use this cmdlet to remove the specified folder.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMFolder](Get-CMFolder)



* [New-CMFolder](New-CMFolder)



* [Set-CMFolder](Set-CMFolder)





---


### Examples
#### Example 1
```PowerShell
$parentPath = 'DeviceCollection'
$name = 'Folder1'
$name2 = 'Folder2'
$name3 = 'Folder3'
Remove-CMFolder -Name $name3 -ParentContainerNode (Get-CMFolder -Name $name2) -Force
```

#### Example 2
```PowerShell
(Get-CMFolder -Name $name2) | Remove-CMFolder -Force
```

#### Example 3
```PowerShell
Remove-CMFolder -FolderPath  ($parentPath + '\' + $name) -Force
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FolderPath**

Specify the path to the console folder. For example, `DeviceCollection\Folder1`






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Force**

Add this parameter to run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Guid**

Specify the GUID of the console folder to remove.






|Type    |Required|Position|PipelineInput|Aliases   |
|--------|--------|--------|-------------|----------|
|`[Guid]`|true    |named   |False        |FolderGuid|



#### **Id**

Specify the ID of the console folder to remove.






|Type     |Required|Position|PipelineInput|Aliases        |
|---------|--------|--------|-------------|---------------|
|`[Int32]`|true    |named   |False        |ContainerNodeID|



#### **InputObject**

Specify a folder object. To get this object, use the Get-CMFolder (Get-CMFolder.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases      |
|-----------------|--------|--------|--------------|-------------|
|`[IResultObject]`|true    |named   |True (ByValue)|ContainerNode|



#### **Name**

Specify the name of the console folder to remove.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ParentContainerNode**

Specify a folder object for the parent container. To get this object, use the Get-CMFolder (Get-CMFolder.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **ParentFolderPath**

Specify the path of the parent folder.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
Remove-CMFolder [-DisableWildcardHandling] -FolderPath <String> [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMFolder [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Guid <Guid> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMFolder [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <Int32> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMFolder [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMFolder [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> [-ParentContainerNode <IResultObject>] [-ParentFolderPath <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
