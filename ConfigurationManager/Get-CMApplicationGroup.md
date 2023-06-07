Get-CMApplicationGroup
----------------------




### Synopsis
Get an application group.



---


### Description

Use this cmdlet to get an application group. Use an application group to deploy multiple applications to a collection as a single deployment. The metadata you specify about the app group is seen in Software Center as a single entity. You can order the apps in the group so that the client installs them in a specific order. For more information, see Create application groups (/mem/configmgr/apps/deploy-use/create-app-groups).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMApplicationGroup](New-CMApplicationGroup)



* [Remove-CMApplicationGroup](Remove-CMApplicationGroup)



* [Set-CMApplicationGroup](Set-CMApplicationGroup)



* [Get-CMApplicationGroupDeployment](Get-CMApplicationGroupDeployment)



* [New-CMApplicationGroupDeployment](New-CMApplicationGroupDeployment)



* [Remove-CMApplicationGroupDeployment](Remove-CMApplicationGroupDeployment)



* [Set-CMApplicationGroupDeployment](Set-CMApplicationGroupDeployment)



* [Create application groups](Create application groups)





---


### Examples
#### Example 1
```PowerShell
Get-CMApplicationGroup -Name 'Central app'
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



#### **Id**

Specify the ID of the app group to get. This value is the same as the CI_ID , for example `1025866`.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |named   |False        |CIId<br/>CI_ID|



#### **ModelName**

Specify the application model identifier of the app group to get. This value is also known as the CI Unique ID . For example, `ScopeId_0D7D8B60-F2F9-484A-B9F3-4A8B68D14D59/ApplicationGroup_047fbf05-55f4-42ab-9581-e63fd0337fed`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Name**

Specify the name of the app group to get.






|Type      |Required|Position|PipelineInput|Aliases                                      |
|----------|--------|--------|-------------|---------------------------------------------|
|`[String]`|false   |0       |False        |LocalizedDisplayName<br/>ApplicationGroupName|



#### **ShowHidden**

Add this parameter to show hidden application groups. A hidden app group has the IsHidden property set to `$true`. A hidden app group doesn't display in the Configuration Manager console, and it only returns with this cmdlet when you specify this parameter.


To hide an app group, use the following commands:






$appGroup = Get-CMApplicationGroup -Name "test app group" $appGroup.IsHidden = $true $appGroup.Put()







|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_ApplicationGroup


* IResultObject#SMS_ApplicationGroup






---


### Notes
This cmdlet returns the SMS_ApplicationGroup WMI class object.



---


### Syntax
```PowerShell
Get-CMApplicationGroup [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <Int32> [-ShowHidden] [<CommonParameters>]
```
```PowerShell
Get-CMApplicationGroup [-DisableWildcardHandling] [-ForceWildcardHandling] -ModelName <String> [-ShowHidden] [<CommonParameters>]
```
```PowerShell
Get-CMApplicationGroup [[-Name] <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-ShowHidden] [<CommonParameters>]
```
