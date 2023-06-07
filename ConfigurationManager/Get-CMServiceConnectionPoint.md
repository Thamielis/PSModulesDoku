Get-CMServiceConnectionPoint
----------------------------




### Synopsis
Gets a service connection point.



---


### Description

The Get-CMServiceConnectionPoint cmdlet gets a service connection point.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMServiceConnectionPoint](Add-CMServiceConnectionPoint)



* [Get-CMSiteSystemServer](Get-CMSiteSystemServer)



* [Remove-CMServiceConnectionPoint](Remove-CMServiceConnectionPoint)



* [Set-CMServiceConnectionPoint](Set-CMServiceConnectionPoint)





---


### Examples
#### Example 1: Get a service connection point by name
```PowerShell
PS XYZ:\> Get-CMServiceConnectionPoint -SiteSystemServerName "TestServer01.Contoso.com" -SiteCode PS1
```
This command gets the service connection point for the site system server named TestServer01.Contoso.com with the site code PS1.
#### Example 2: Get a service connection point by using a variable
```PowerShell
PS XYZ:\> $Server = Get-CMSiteSystemServer -SiteCode PS1 -SiteSystemServerName "TestServer02.Contoso.com"
PS XYZ:\> Get-CMServiceConnectionPoint -InputObject $Server
```
The first command gets the site system server object named TestServer02.Contoso.com with the site code PS1 and saves the object in the $Server variable.


The second command gets the service connection point for the server stored in $Server.


---


### Parameters
#### **AllSite**








|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[Switch]`|false   |named   |False        |AllSites|



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

Specifies a site system server object. To obtain a site system server object, use the Get-CMSiteSystemServer cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **SiteCode**

Specifies the site code for a Configuration Manager site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies the name of a site system server that hosts the service connection point role.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|false   |0       |False        |Name<br/>ServerName|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_SCI_SysResUse


* IResultOBject#SMS_SCI_SysResUse






---


### Notes




---


### Syntax
```PowerShell
Get-CMServiceConnectionPoint [-AllSite] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMServiceConnectionPoint [[-SiteSystemServerName] <String>] [-AllSite] [-DisableWildcardHandling] [-ForceWildcardHandling] [-SiteCode <String>] [<CommonParameters>]
```
