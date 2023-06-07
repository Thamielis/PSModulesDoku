New-CMBaseline
--------------




### Synopsis
Create a configuration baseline.



---


### Description

Use this cmdlet to create a configuration baseline. A baseline is a collection of configuration items that Configuration Manager uses to evaluate whether a computer complies with software requirements. For more information, see Create configuration baselines in Configuration Manager (/mem/configmgr/compliance/deploy-use/create-configuration-baselines).



After you create a baseline, use the Set-CMBaseline (Set-CMBaseline.md) cmdlet to add configuration items. Then use the [New-CMBaselineDeployment](New-CMBaselineDeployment.md)cmdlet to deploy the baseline to a collection. When deployed, devices in that collection download the configuration baseline and assess compliance with it.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Disable-CMBaseline](Disable-CMBaseline)



* [Enable-CMBaseline](Enable-CMBaseline)



* [Export-CMBaseline](Export-CMBaseline)



* [Get-CMBaseline](Get-CMBaseline)



* [Import-CMBaseline](Import-CMBaseline)



* [Remove-CMBaseline](Remove-CMBaseline)



* [Set-CMBaseline](Set-CMBaseline)



* [New-CMBaselineDeployment](New-CMBaselineDeployment)



* [Create configuration baselines in Configuration Manager](Create configuration baselines in Configuration Manager)





---


### Examples
#### Example 1: Create a configuration baseline
```PowerShell
New-CMBaseline -Name "Accounting Department baseline" -Description "Compliance standards for Accounting computers."
```



---


### Parameters
#### **AllowComanagedClients**

Add this parameter to always apply this baseline even for co-managed clients.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Category**

Specify an array of configuration category names to add to the configuration baselines. These categories improve searching and filtering. By default, the site includes the following categories for configuration baselines:


* Client


* IT Infrastructure


* Line of Business


* Server




To use another category, first add it with the New-CMCategory (New-CMCategory.md)cmdlet and `-CategoryType BaselineCategories` parameter.







|Type        |Required|Position|PipelineInput|Aliases                       |
|------------|--------|--------|-------------|------------------------------|
|`[String[]]`|false   |named   |False        |LocalizedCategoryInstanceNames|



#### **Description**

Specify an optional description for the baseline to help identify it.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |named   |False        |LocalizedDescription|



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



#### **Name**

Specify a name for the configuration baseline.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |named   |False        |LocalizedDisplayName|



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
* IResultObject#SMS_ConfigurationBaselineInfo






---


### Notes
For more information on this return object and its properties, see SMS_ConfigurationBaselineInfo server WMI class (/mem/configmgr/develop/reference/compliance/sms_configurationbaselineinfo-server-wmi-class).



---


### Syntax
```PowerShell
New-CMBaseline [-AllowComanagedClients] [-Category <String[]>] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
