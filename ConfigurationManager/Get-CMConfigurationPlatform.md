Get-CMConfigurationPlatform
---------------------------




### Synopsis
Get an OS platform for a requirement rule.



---


### Description

Use this cmdlet to get an OS platform to use with an OS requirement rule for an application deployment type. You can use the output object of this cmdlet with the New-CMRequirementRuleOperatingSystemValue cmdlet.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMRequirementRuleOperatingSystemValue](New-CMRequirementRuleOperatingSystemValue)





---


### Examples
#### Example 1: Add a requirement rule for an OS by platform
```PowerShell
$myGC = Get-CMGlobalCondition -Name "Operating System" | Where-Object PlatformType -eq 1

$platformA = Get-CMConfigurationPlatform -Name "All Windows Server 2019 and higher (64-bit)"

$platformB = Get-CMConfigurationPlatform -Name "All Windows Server 2016 and higher (64-bit)"

$myRule = $myGC | New-CMRequirementRuleOperatingSystemValue -RuleOperator OneOf -Platform $platformA, $platformB

Set-CMScriptDeploymentType -ApplicationName "Central App" -DeploymentTypeName "Install" -AddRequirement $myRule
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

Specify the integer value for the CI_ID of the platform. For example, the CI_ID for the platform All Windows Server 2019 and higher (64-bit) is `287650`.


Use a command similar to the following to discover the CI_ID for a platform:


`Get-CMConfigurationPlatform -Name " Server 2019 " | Select-Object LocalizedDisplayName, CI_ID`






|Type     |Required|Position|PipelineInput|Aliases|
|---------|--------|--------|-------------|-------|
|`[Int32]`|true    |0       |False        |CI_ID  |



#### **IsSupported**

Configuration Manager still defines legacy platforms for backward compatibility. Set this parameter to `$true` to filter the results to only platforms that are currently supported.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Name**

Specify the name of the OS platform. You can use wildcard characters:


* `*`: Multiple characters


* `?`: Single character






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |0       |False        |LocalizedDisplayName|



#### **PlatformOption**

Use this parameter to filter the results by platform type.



Valid Values:

* None
* Windows
* Mobile
* Mac
* MixedPlatform






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[PlatformType]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_ConfigurationPlatform


* IResultObject#SMS_ConfigurationPlatform






---


### Notes
For more information on this return object and its properties, see SMS_ConfigurationPlatform server WMI class (/mem/configmgr/develop/reference/compliance/sms_configurationplatform-server-wmi-class).

This cmdlet is different from the similar Get-CMSupportedPlatform cmdlet.



---


### Syntax
```PowerShell
Get-CMConfigurationPlatform [-Id] <Int32> [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-IsSupported <Boolean>] [-PlatformOption {None | Windows | Mobile | Mac | MixedPlatform}] [<CommonParameters>]
```
```PowerShell
Get-CMConfigurationPlatform [[-Name] <String>] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-IsSupported <Boolean>] [-PlatformOption {None | Windows | Mobile | Mac | MixedPlatform}] [<CommonParameters>]
```
