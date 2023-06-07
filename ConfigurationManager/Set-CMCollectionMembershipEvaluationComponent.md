Set-CMCollectionMembershipEvaluationComponent
---------------------------------------------




### Synopsis
Configure the site component that evaluates collection membership.



---


### Description

Use this cmdlet to configure the site component that evaluates collection membership. This component controls how often collection membership is incrementally evaluated. Incremental evaluation updates a collection membership with only new or changed resources.



For more information, see Site components for Configuration Manager (/mem/configmgr/core/servers/deploy/configure/site-components#bkmk_colleval).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMCollectionMembershipEvaluationComponent](Get-CMCollectionMembershipEvaluationComponent)



* [Get-CMSiteComponent](Get-CMSiteComponent)



* [Site components for Configuration Manager](Site components for Configuration Manager)



* [Collection evaluation in Configuration Manager](Collection evaluation in Configuration Manager)





---


### Examples
#### Example 1: Set an evaluation interval
```PowerShell
Set-CMCollectionMembershipEvaluationComponent -EvaluationMins 10 -SiteCode "XYZ"
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EvaluationMins**

Specify an integer value for the number of minutes for the evaluation interval. By default, this value is 5 minutes.






|Type     |Required|Position|PipelineInput|Aliases        |
|---------|--------|--------|-------------|---------------|
|`[Int32]`|true    |named   |False        |MinutesInterval|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SiteCode**

Specify the three-character site code to configure this component.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

This parameter is deprecated, don't use it.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |named   |False        |Name   |



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
None





---


### Outputs
* IResultObject#SMS_SCI_Component






---


### Notes
For more information on this return object and its properties, see SMS_SCI_Component server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms_sci_component-server-wmi-class).



---


### Syntax
```PowerShell
Set-CMCollectionMembershipEvaluationComponent [-DisableWildcardHandling] -EvaluationMins <Int32> [-ForceWildcardHandling] [-PassThru] [-SiteCode <String>] [-SiteSystemServerName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
