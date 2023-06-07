Get-CMFolder
------------




### Synopsis
Get one or more folders in the console.



---


### Description

Use this cmdlet to get all customized folders or folders from the specified parent path.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMFolder](New-CMFolder)



* [Remove-CMFolder](Remove-CMFolder)



* [Set-CMFolder](Set-CMFolder)





---


### Examples
#### Example 1
```PowerShell
$parentPath = 'DeviceCollection'
$name = 'Folder1'
$name2 = 'Folder2'
$name3 = 'Folder3'
$root = New-CMFolder -ParentFolderPath $parentPath -Name $name
$folder = Get-CMFolder -FolderPath ($parentPath + '\' + $name + '\' + $name2 + '\' +$name3)
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

Specify the GUID of the console folder.






|Type    |Required|Position|PipelineInput|Aliases   |
|--------|--------|--------|-------------|----------|
|`[Guid]`|true    |named   |False        |FolderGuid|



#### **Id**

Specify the ID of the console folder.






|Type     |Required|Position|PipelineInput|Aliases        |
|---------|--------|--------|-------------|---------------|
|`[Int32]`|true    |named   |False        |ContainerNodeID|



#### **InputObject**

Specify a folder object for the parent container.






|Type             |Required|Position|PipelineInput |Aliases            |
|-----------------|--------|--------|--------------|-------------------|
|`[IResultObject]`|false   |named   |True (ByValue)|ParentContainerNode|



#### **IsEmpty**

Set this parameter to `$true` to filter the results by empty folders.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **IsSearchFolder**

Set this parameter to `$true` to filter the results by search folders.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Name**

Specify the name of the console folder.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |0       |False        |



#### **ParentFolderPath**

Specify the path of the parent folder.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteCode**

Specify the three-character code for the site.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|false   |named   |False        |SourceSite|



#### **TypeName**

Specify the type to filter the results. For example:


* `SMS_Collection_Device`


* `SMS_Package`


* `SMS_Driver`






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[String]`|false   |named   |False        |ObjectTypeName|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_ObjectContainerNode


* IResultObject#SMS_ObjectContainerNode






---


### Notes
For more information on this return object and its properties, see SMS_ObjectContainerNode server WMI class (/mem/configmgr/develop/reference/core/servers/console/sms_objectcontainernode-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMFolder [-DisableWildcardHandling] -FolderPath <String> [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMFolder [-DisableWildcardHandling] [-ForceWildcardHandling] -Guid <Guid> [<CommonParameters>]
```
```PowerShell
Get-CMFolder [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <Int32> [<CommonParameters>]
```
```PowerShell
Get-CMFolder [[-Name] <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-InputObject <IResultObject>] [-IsEmpty <Boolean>] [-IsSearchFolder <Boolean>] [-ParentFolderPath <String>] [-SiteCode <String>] [-TypeName <String>] [<CommonParameters>]
```
