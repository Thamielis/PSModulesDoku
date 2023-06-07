Get-CMComplianceSetting
-----------------------




### Synopsis
Get a setting for a configuration item.



---


### Description

Use this cmdlet to get a setting for a configuration item. Settings represent the business or technical conditions to assess compliance on client devices. Configure a new setting or browse to an existing setting on a reference computer. For more information, see Get started with compliance settings in Configuration Manager (/mem/configmgr/compliance/get-started/get-started-with-compliance-settings).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMConfigurationItem](Get-CMConfigurationItem)



* [Get-CMComplianceRule](Get-CMComplianceRule)





---


### Examples
#### Example 1: Get the location for a setting in a configuration item
```PowerShell
Get-CMComplianceSetting -Name "Windows health check" -SettingName "appevents" -Fast | Select-Object Location
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

Specify the CI_ID for the configuration item that has the setting you want to get. For example, `258895`.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|true    |0       |False        |



#### **InputObject**

Specify a configuration item object that has the setting you want to get. To get this object, use the Get-CMConfigurationItem (Get-CMConfigurationItem.md).






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specify the name of the configuration item that has the setting you want to get.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName|



#### **SettingName**

Specify the name of the setting in the configuration item. This value is the same as the Name value on the Settings tab of the configuration item properties in the console.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* Microsoft.ConfigurationManagement.DesiredConfigurationManagement.ConfigurationItemSetting






---


### Notes




---


### Syntax
```PowerShell
Get-CMComplianceSetting [-Id] <Int32> [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-SettingName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMComplianceSetting [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] -InputObject <IResultObject> [-SettingName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMComplianceSetting [-Name] <String> [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-SettingName <String>] [<CommonParameters>]
```
