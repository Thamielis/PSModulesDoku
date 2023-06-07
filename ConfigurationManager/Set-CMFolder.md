Set-CMFolder
------------




### Synopsis
Configure a folder in the console.



---


### Description

Use this cmdlet to configure the specified folder. For example, rename it or move it to another folder.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMFolder](Get-CMFolder)



* [New-CMFolder](New-CMFolder)



* [Remove-CMFolder](Remove-CMFolder)





---


### Examples
#### Example 1
```PowerShell
$parentPath = 'DeviceCollection'
$name =  'Folder1'
$name2 =  'Folder2'
$name3 =  'Folder3'
$root = New-CMFolder -ParentFolderPath $parentPath -Name $name
Set-CMFolder -Name $name2 -ParentContainerNode (Get-CMFolder -Name $name) -NewName $newName
```

#### Example 2
```PowerShell
(Get-CMFolder -Name $newName) | Set-CMFolder -NewName $name2
```

#### Example 3
```PowerShell
$folder = Set-CMFolder -Name $name3 -ParentFolderPath ($parentPath + '\' + $name + '\' + $name2) -MoveToFolder $root
```

#### Example 4
```PowerShell
$folder = Set-CMFolder -Guid $sub2.FolderGuid -MoveToPath ($parentPath + '\' + $name + '\' + $name2)
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



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Guid**

Specify the GUID of the console folder to configure.






|Type    |Required|Position|PipelineInput|Aliases   |
|--------|--------|--------|-------------|----------|
|`[Guid]`|true    |named   |False        |FolderGuid|



#### **Id**

Specify the ID of the console folder to configure.






|Type     |Required|Position|PipelineInput|Aliases        |
|---------|--------|--------|-------------|---------------|
|`[Int32]`|true    |named   |False        |ContainerNodeID|



#### **InputObject**

Specify a folder object to configure. To get this object, use the Get-CMFolder (Get-CMFolder.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases      |
|-----------------|--------|--------|--------------|-------------|
|`[IResultObject]`|true    |named   |True (ByValue)|ContainerNode|



#### **MoveToFolder**

To move a folder, specify the target folder object. To get this object, use the Get-CMFolder (Get-CMFolder.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **MoveToPath**

To move a folder, specify the path to the target folder.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Name**

Specify the name of the console folder to configure.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **NewName**

Use this parameter to rename the folder.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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
Set-CMFolder [-DisableWildcardHandling] -FolderPath <String> [-ForceWildcardHandling] [-MoveToFolder <IResultObject>] [-MoveToPath <String>] [-NewName <String>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMFolder [-DisableWildcardHandling] [-ForceWildcardHandling] -Guid <Guid> [-MoveToFolder <IResultObject>] [-MoveToPath <String>] [-NewName <String>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMFolder [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <Int32> [-MoveToFolder <IResultObject>] [-MoveToPath <String>] [-NewName <String>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMFolder [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-MoveToFolder <IResultObject>] [-MoveToPath <String>] [-NewName <String>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMFolder [-DisableWildcardHandling] [-ForceWildcardHandling] [-MoveToFolder <IResultObject>] [-MoveToPath <String>] -Name <String> [-NewName <String>] [-ParentContainerNode <IResultObject>] [-ParentFolderPath <String>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
