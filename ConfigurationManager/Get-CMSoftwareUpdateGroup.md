Get-CMSoftwareUpdateGroup
-------------------------




### Synopsis
Gets software update groups.



---


### Description

The Get-CMSoftwareUpdateGroup cmdlet gets one or more software update groups in Configuration Manager. A software update group is a collection of one or more software updates. You can add software updates to a software update group and then deploy the group to clients. After you deploy a software update group, you can add new software updates to the group and Configuration Manager automatically deploys them.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMSoftwareUpdateGroup](New-CMSoftwareUpdateGroup)



* [Remove-CMSoftwareUpdateGroup](Remove-CMSoftwareUpdateGroup)



* [Set-CMSoftwareUpdateGroup](Set-CMSoftwareUpdateGroup)





---


### Examples
#### Example 1: Get software update groups
```PowerShell
PS XYZ:\> Get-CMSoftwareUpdateGroup
```
This command gets all software update groups.
#### Example 2: Get a software update group by using an ID
```PowerShell
PS XYZ:\> Get-CMSoftwareUpdateGroup -Id "ST10000D"
```
This command gets a software update group that has the ID ST10000D.
#### Example 3: Get a software update group by using a name
```PowerShell
PS XYZ:\> Get-CMSoftwareUpdateGroup -Name "SUGroupD01"
```
This command gets a software update group object named SUGroupD01.


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

Specifies an array of IDs of software update groups.






|Type       |Required|Position|PipelineInput|Aliases       |
|-----------|--------|--------|-------------|--------------|
|`[Int32[]]`|true    |named   |False        |CIId<br/>CI_ID|



#### **Name**

Specifies an array of names of software update groups.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |named   |False        |LocalizedDisplayName|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_AuthorizationList


* IResultObject#SMS_AuthorizationList






---


### Notes




---


### Syntax
```PowerShell
Get-CMSoftwareUpdateGroup [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <Int32[]> [<CommonParameters>]
```
```PowerShell
Get-CMSoftwareUpdateGroup [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
