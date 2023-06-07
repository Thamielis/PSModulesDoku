Get-CMCollectionMembershipEvaluationComponent
---------------------------------------------




### Synopsis
Get the site component that evaluates collection membership.



---


### Description

Use this cmdlet to get the site component that evaluates collection membership. This component controls how often collection membership is incrementally evaluated. Incremental evaluation updates a collection membership with only new or changed resources.



For more information, see Site components for Configuration Manager (/mem/configmgr/core/servers/deploy/configure/site-components#bkmk_colleval).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMCollectionMembershipEvaluationComponent](Set-CMCollectionMembershipEvaluationComponent)



* [Get-CMSiteComponent](Get-CMSiteComponent)



* [Site components for Configuration Manager](Site components for Configuration Manager)



* [Collection evaluation in Configuration Manager](Collection evaluation in Configuration Manager)





---


### Examples
#### Example 1: Get an evaluation period for the site
```PowerShell
$component = Get-CMCollectionMembershipEvaluationComponent -SiteCode "XYZ"

$component.Props | Where-Object { $_.PropertyName -eq "Incremental Interval" } | Select-Object Value
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



#### **SiteCode**

Specify the three-character site code to query for this component.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

This parameter is deprecated, don't use it.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |named   |False        |Name   |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_SCI_Component


* IResultObject#SMS_SCI_Component






---


### Notes
For more information on this return object and its properties, see SMS_SCI_Component server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms_sci_component-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMCollectionMembershipEvaluationComponent [-DisableWildcardHandling] [-ForceWildcardHandling] [-SiteCode <String>] [-SiteSystemServerName <String>] [<CommonParameters>]
```
