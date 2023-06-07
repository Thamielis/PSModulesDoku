New-CMRequirementRuleOperatingSystemValue
-----------------------------------------




### Synopsis
Create an OS requirement rule for an application deployment type.



---


### Description

Use this cmdlet to create an OS requirement rule for an application deployment type.



After you use this cmdlet, then use one of the Add- or Set- cmdlets for deployment types. Pass this requirement rule object to either the AddRequirement or RemoveRequirement parameters.



For more information, see Deployment type Requirements (/mem/configmgr/apps/deploy-use/create-applications#bkmk_dt-require) and [Create global conditions](/mem/configmgr/apps/deploy-use/create-global-conditions).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMConfigurationPlatform](Get-CMConfigurationPlatform)



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



* [New-CMRequirementRuleOperatingSystemLanguageValue](New-CMRequirementRuleOperatingSystemLanguageValue)



* [New-CMRequirementRuleOUValue](New-CMRequirementRuleOUValue)



* [New-CMRequirementRuleRegistryKeyPermissionValue](New-CMRequirementRuleRegistryKeyPermissionValue)



* [New-CMRequirementRuleScreenResolutionValue](New-CMRequirementRuleScreenResolutionValue)



* [Get-CMGlobalCondition](Get-CMGlobalCondition)



* [Deployment type Requirements](Deployment type Requirements)



* [Create global conditions](Create global conditions)





---


### Examples
#### Example 1: Add a requirement rule for an OS by platform
```PowerShell
$myGC = Get-CMGlobalCondition -Name "Operating System" | Where-Object PlatformType -eq 1

$platformA = Get-CMConfigurationPlatform -Name "All Windows Server 2019 and higher (64-bit)" -Fast

$platformB = Get-CMConfigurationPlatform -Name "All Windows Server 2016 and higher (64-bit)" -Fast

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



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify a global condition object to use as the basis for this requirement rule. To get this object, use the Get-CMGlobalCondition (Get-CMGlobalCondition.md)cmdlet.


In most instances, you'll use the default Operating system global condition for non-mobile Windows devices. For example: `Get-CMGlobalCondition -Name "Operating System" | Where-Object PlatformType -eq 1`.


> [!NOTE] > By default, Configuration Manager has two global conditions named Operating system . You can distinguish them by device type using the PlatformType property: > > |PlatformType|Device type| > |---------|---------| > |`1`|Windows| > |`2`|Mobile|






|Type             |Required|Position|PipelineInput |Aliases        |
|-----------------|--------|--------|--------------|---------------|
|`[IResultObject]`|true    |0       |True (ByValue)|GlobalCondition|



#### **Platform**

Specify an array of one or more OS platform objects. To get this object, use the Get-CMConfigurationPlatform (Get-CMConfigurationPlatform.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases  |
|-------------------|--------|--------|-------------|---------|
|`[IResultObject[]]`|false   |named   |False        |Platforms|



#### **PlatformString**

Instead of using the Get-CMConfigurationPlatform cmdlet with the Platform parameter, you can use this parameter to specify an array of one or more known ModelName strings. For example, the ModelName for the platform All Windows 11 and higher (64-bit) is `Windows/All_x64_Windows_11_and_higher_Clients`.


Use a command similar to the following to discover the model name for a platform:


`Get-CMConfigurationPlatform -Name " Server 2019 " -Fast | Select-Object LocalizedDisplayName, ModelName`






|Type        |Required|Position|PipelineInput|Aliases                                                       |
|------------|--------|--------|-------------|--------------------------------------------------------------|
|`[String[]]`|false   |named   |False        |PlatformStrings<br/>PlatformCIUniqueID<br/>PlatformCIUniqueIDs|



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



#### **SelectFullPlatform**

Use this parameter to select all platforms of the specified type.



Valid Values:

* Windows
* Nokia
* WindowsMobile
* IOs
* IOsDeepLink
* Android
* AndroidDeepLink
* Mac
* WinPhone8
* WinPhone8DeepLink
* MobileMsi






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[FullPlatformOption]`|false   |named   |False        |





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
New-CMRequirementRuleOperatingSystemValue [-InputObject] <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Platform <IResultObject[]>] [-PlatformString <String[]>] -RuleOperator {OneOf | NoneOf} [-SelectFullPlatform {Windows | Nokia | WindowsMobile | IOs | IOsDeepLink | Android | AndroidDeepLink | Mac | WinPhone8 | WinPhone8DeepLink | MobileMsi}] [<CommonParameters>]
```