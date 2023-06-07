Get-CMComplianceRule
--------------------




### Synopsis
Get a compliance rule for a configuration item.



---


### Description

Get a compliance rule for a configuration item. Compliance rules specify the conditions that define the compliance of a configuration item setting. Before the client evaluates a setting for compliance, it must have at least one compliance rule. For more information, see Get started with compliance settings in Configuration Manager (/mem/configmgr/compliance/get-started/get-started-with-compliance-settings).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMConfigurationItem](Get-CMConfigurationItem)



* [Get-CMComplianceSetting](Get-CMComplianceSetting)





---


### Examples
#### Example 1: Get a compliance rule for a configuration item
```PowerShell
Get-CMComplianceRule -Name "BitLocker data drive protection" -RuleName "06 must exist" -Fast
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Fast**

Add this parameter to not automatically refresh lazy properties. Lazy properties contain values that are relatively inefficient to retrieve. Getting these properties can cause additional network traffic and decrease cmdlet performance.


If you don't use this parameter, the cmdlet displays a warning. To disable this warning, set `$CMPSSuppressFastNotUsedCheck = $true`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the CI_ID for the configuration item that has the compliance rule you want to get. For example, `258895`.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|true    |0       |False        |



#### **InputObject**

Specify a configuration item object that has the compliance rule you want to get. To get this object, use the Get-CMConfigurationItem (Get-CMConfigurationItem.md).






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specify the name of the configuration item that has the compliance rule you want to get.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName|



#### **PropertyPath**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **RuleName**

Specify the name of the compliance rule in the configuration item. This value is the same as the Name value on the Compliance Rules tab of the configuration item properties in the console.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* Microsoft.SystemsManagementServer.DesiredConfigurationManagement.Rules.Rule






---


### Notes




---


### Syntax
```PowerShell
Get-CMComplianceRule [-Id] <Int32> [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-PropertyPath <String>] [-RuleName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMComplianceRule [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] -InputObject <IResultObject> [-PropertyPath <String>] [-RuleName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMComplianceRule [-Name] <String> [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-PropertyPath <String>] [-RuleName <String>] [<CommonParameters>]
```
