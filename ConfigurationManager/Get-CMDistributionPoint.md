Get-CMDistributionPoint
-----------------------




### Synopsis
Gets a distribution point.



---


### Description

The Get-CMDistributionPoint cmdlet gets a distribution point.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMDistributionPoint](Add-CMDistributionPoint)



* [Get-CMDistributionPointGroup](Get-CMDistributionPointGroup)



* [Remove-CMDistributionPoint](Remove-CMDistributionPoint)



* [Set-CMDistributionPoint](Set-CMDistributionPoint)



* [Update-CMDistributionPoint](Update-CMDistributionPoint)



* [Get-CMDistributionPointGroup](Get-CMDistributionPointGroup)





---


### Examples
#### Example 1: Get a distribution point
```PowerShell
PS XYZ:\> Get-CMDistributionPoint -SiteSystemServerName "MySiteSys_11310.contoso.com"
```
This command gets the distribution point for the site system server named MySiteSys_11310.contoso.com.
#### Example 2: Get a distribution point by using the pipeline
```PowerShell
PS XYZ:\> Get-CMDistributionPointGroup -Name "DPGroup" | Get-CMDistributionPoint
```
This command gets the distribution point group object named DPGroup and uses the pipeline operator to pass the object to Get-CMDistributionPoint , which gets all of the distribution points for the distribution point group object.


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



#### **DistributionPointGroup**

Specifies a distribution point group object. To obtain a distribution point group object, use the Get-CMDistributionPointGroup (Get-CMDistributionPointGroup.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **DistributionPointGroupId**

Specifies the ID of a distribution point group.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DistributionPointGroupName**

Specifies the name of a distribution point group.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specifies a site system server object. To obtain a site system server object, use the Get-CMSiteSystemServer (Get-CMSiteSystemServer.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **SiteCode**

Specifies the site code of the site that is associated with a distribution point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies a fully qualified domain name (FQDN) of the server that hosts the site system role.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|false   |0       |False        |Name<br/>ServerName|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_SCI_SysResUse


* IResultObject#SMS_SCI_SysResUse






---


### Notes




---


### Syntax
```PowerShell
Get-CMDistributionPoint [-AllSite] [-DisableWildcardHandling] -DistributionPointGroup <IResultObject> [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMDistributionPoint [-AllSite] [-DisableWildcardHandling] -DistributionPointGroupId <String> [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMDistributionPoint [-AllSite] [-DisableWildcardHandling] -DistributionPointGroupName <String> [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMDistributionPoint [-AllSite] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMDistributionPoint [[-SiteSystemServerName] <String>] [-AllSite] [-DisableWildcardHandling] [-ForceWildcardHandling] [-SiteCode <String>] [<CommonParameters>]
```
