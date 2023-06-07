Get-CMSoftwareUpdateAutoDeploymentRule
--------------------------------------




### Synopsis
Get an automatic deployment rule for software updates.



---


### Description

The Get-CMSoftwareUpdateAutoDeploymentRule cmdlet gets the specified automatic deployment rules for software updates.



Configuration Manager uses rules to manage automatic deployment of software updates. When a rule runs, Configuration Manager adds updates that qualify for the rule to a software update group. The Configuration Manager server downloads content files and copies them to distribution points, and then updates client computers.



You can specify rules by ID or by name. You can use this cmdlet to get deployment rules for automatic software updates to use with other cmdlets. For example, the Invoke-CMSoftwareUpdateAutoDeploymentRule (Invoke-CMSoftwareUpdateAutoDeploymentRule.md) or [Remove-CMSoftwareUpdateAutoDeploymentRule](Remove-CMSoftwareUpdateAutoDeploymentRule.md)cmdlets.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Disable-CMSoftwareUpdateAutoDeploymentRule](Disable-CMSoftwareUpdateAutoDeploymentRule)



* [Enable-CMSoftwareUpdateAutoDeploymentRule](Enable-CMSoftwareUpdateAutoDeploymentRule)



* [Invoke-CMSoftwareUpdateAutoDeploymentRule](Invoke-CMSoftwareUpdateAutoDeploymentRule)



* [New-CMSoftwareUpdateAutoDeploymentRule](New-CMSoftwareUpdateAutoDeploymentRule)



* [Remove-CMSoftwareUpdateAutoDeploymentRule](Remove-CMSoftwareUpdateAutoDeploymentRule)



* [Set-CMSoftwareUpdateAutoDeploymentRule](Set-CMSoftwareUpdateAutoDeploymentRule)





---


### Examples
#### Example 1: Get an ADR by name
```PowerShell
Get-CMSoftwareUpdateAutoDeploymentRule -Name "Weekly Driver Updates"
```

#### Example 2: Get an ADR by ID
```PowerShell
Get-CMSoftwareUpdateAutoDeploymentRule -Id "33"
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

Specify an array of automatic deployment rule IDs to configure. This value is the AutoDeploymentID property of the ADR object.






|Type       |Required|Position|PipelineInput|Aliases         |
|-----------|--------|--------|-------------|----------------|
|`[Int32[]]`|true    |0       |False        |AutoDeploymentId|



#### **IsServicingPlan**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Name**

Specifies a name of a rule for automatic deployment of software updates.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |0       |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_AutoDeployment


* IResultObject#SMS_AutoDeployment






---


### Notes
The SMS_AutoDeployment output object displays many of the ADR settings as the stored XML. Parse this XML for specific settings.

For example:

- The -Language parameter is stored in the UpdateRuleXML property as `<MatchRules><string>'Locale:10'</string></MatchRules>` - The -LanguageSelection parameter is stored in the ContentTemplate property as `<ContentLocales><Locale>Locale:10</Locale></ContentLocales>`

These locale codes are stored as the decimal equivalent of the Windows language ID. For example, `9` is `0x0009` for English, and `10` is `0x000A` for Spanish. For more information, see [MS-LCID]: Windows Language Code Identifier (LCID) Reference (/openspecs/windows_protocols/ms-lcid/a9eac961-e77d-41a6-90a5-ce1a8b0cdb9c).



---


### Syntax
```PowerShell
Get-CMSoftwareUpdateAutoDeploymentRule [-Id] <Int32[]> [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-IsServicingPlan <Boolean>] [<CommonParameters>]
```
```PowerShell
Get-CMSoftwareUpdateAutoDeploymentRule [[-Name] <String>] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-IsServicingPlan <Boolean>] [<CommonParameters>]
```
