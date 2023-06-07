New-CMRequirementRuleOperatingSystemLanguageValue
-------------------------------------------------




### Synopsis
Create an OS language requirement rule for an application deployment type.



---


### Description

Use this cmdlet to create an OS language requirement rule for an application deployment type.



After you use this cmdlet, then use one of the Add- or Set- cmdlets for deployment types. Pass this requirement rule object to either the AddRequirement or RemoveRequirement parameters.



For more information, see Deployment type Requirements (/mem/configmgr/apps/deploy-use/create-applications#bkmk_dt-require) and [Create global conditions](/mem/configmgr/apps/deploy-use/create-global-conditions).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMRequirementRuleActiveDirectorySiteValue](New-CMRequirementRuleActiveDirectorySiteValue)



* [New-CMRequirementRuleBooleanValue](New-CMRequirementRuleBooleanValue)



* [New-CMRequirementRuleCMSiteValue](New-CMRequirementRuleCMSiteValue)



* [New-CMRequirementRuleCommonValue](New-CMRequirementRuleCommonValue)



* [New-CMRequirementRuleDeviceOwnershipValue](New-CMRequirementRuleDeviceOwnershipValue)



* [New-CMRequirementRuleExistential](New-CMRequirementRuleExistential)



* [New-CMRequirementRuleExpression](New-CMRequirementRuleExpression)



* [New-CMRequirementRuleFileAttributeValue](New-CMRequirementRuleFileAttributeValue)



* [New-CMRequirementRuleFilePermissionValue](New-CMRequirementRuleFilePermissionValue)



* [New-CMRequirementRuleFreeDiskSpaceValue](New-CMRequirementRuleFreeDiskSpaceValue)



* [New-CMRequirementRuleInputTypeValue](New-CMRequirementRuleInputTypeValue)



* [New-CMRequirementRuleOperatingSystemValue](New-CMRequirementRuleOperatingSystemValue)



* [New-CMRequirementRuleOUValue](New-CMRequirementRuleOUValue)



* [New-CMRequirementRuleRegistryKeyPermissionValue](New-CMRequirementRuleRegistryKeyPermissionValue)



* [New-CMRequirementRuleScreenResolutionValue](New-CMRequirementRuleScreenResolutionValue)



* [Get-CMGlobalCondition](Get-CMGlobalCondition)



* [Deployment type Requirements](Deployment type Requirements)



* [Create global conditions](Create global conditions)



* [Windows Language Code Identifier (LCID) Reference](Windows Language Code Identifier (LCID) Reference)





---


### Examples
#### Example 1: Add a requirement rule for an OS language
```PowerShell
$myGC = Get-CMGlobalCondition -Name "Operating System Language" | Where-Object PlatformType -eq 1

$cultureA = [System.Globalization.CultureInfo]::GetCultures([System.Globalization.CultureTypes]::AllCultures) | Where-Object Name -eq "ga-IE"

$cultureB = [System.Globalization.CultureInfo]::GetCultures([System.Globalization.CultureTypes]::AllCultures) | Where-Object Name -eq "hu-HU"

$myRule = $myGC | New-CMRequirementRuleOperatingSystemLanguageValue -RuleOperator OneOf -Culture $cultureA,$cultureB -IsMobile $False

Set-CMScriptDeploymentType -ApplicationName "Central App" -DeploymentTypeName "Install" -AddRequirement $myRule
```



---


### Parameters
#### **Culture**

Specify one or more culture objects. Use the following syntax to specify a culture object:


`[System.Globalization.CultureInfo]::GetCultures([System.Globalization.CultureTypes]::AllCultures)`


By default, Windows has over 800 cultures built-in. To filter the results, pass the results of the above command through the pipeline to the Where-Object cmdlet. Filter on one of the following properties:


* LCID : The language code identifier. For example, English (United States) is `1033`. - Name : The language code name. For example, English (United States) is `en-US`. - Display name : The language display name. For example, `English (United States)`.


For more information and a list of cultures, see Windows Language Code Identifier (LCID) Reference (/openspecs/windows_protocols/ms-lcid/a9eac961-e77d-41a6-90a5-ce1a8b0cdb9c).






|Type             |Required|Position|PipelineInput|Aliases |
|-----------------|--------|--------|-------------|--------|
|`[CultureInfo[]]`|true    |named   |False        |Cultures|



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

Specify a global condition object to use as the basis for this requirement rule. To get this object, use the Get-CMGlobalCondition (Get-CMGlobalCondition.md)cmdlet.


In most instances, you'll use the default Operating system language global condition for non-mobile Windows devices. For example: `Get-CMGlobalCondition -Name "Operating System Language" | Where-Object PlatformType -eq 1`.


> [!NOTE] > By default, Configuration Manager has two global conditions named Operating system language . You can distinguish them by device type using the PlatformType property: > > |PlatformType|Device type| > |---------|---------| > |`1`|Windows| > |`2`|Mobile|






|Type             |Required|Position|PipelineInput |Aliases        |
|-----------------|--------|--------|--------------|---------------|
|`[IResultObject]`|true    |0       |True (ByValue)|GlobalCondition|



#### **IsMobile**

If you use the mobile device type global condition, set this parameter to `$true`.


If you get the OS language global condition with `PlatformType -eq 1`, don't include this parameter or set it to `$false`.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **RuleOperator**

Specify the operator to compare the device's setting with the expected value.



Valid Values:

* And
* Or
* Other
* IsEquals
* NotEquals
* GreaterThan
* LessThan
* Between
* NotBetween
* GreaterEquals
* LessEquals
* BeginsWith
* NotBeginsWith
* EndsWith
* NotEndsWith
* Contains
* NotContains
* AllOf
* OneOf
* NoneOf
* SetEquals
* SubsetOf
* ExcludesAll






|Type                      |Required|Position|PipelineInput|
|--------------------------|--------|--------|-------------|
|`[RuleExpressionOperator]`|true    |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
New-CMRequirementRuleOperatingSystemLanguageValue [-InputObject] <IResultObject> -Culture <CultureInfo[]> [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsMobile <Boolean>] -RuleOperator {OneOf | NoneOf} [<CommonParameters>]
```
